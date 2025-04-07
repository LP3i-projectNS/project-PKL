<script setup>
const supabase = useSupabaseClient()
const searchQuery = ref('');
const filteredItems = ref([]);
const selectedItem = ref(null);
const formData = ref({
    status: '',
});

const fetchStudent = async () => {
    if (!searchQuery.value || searchQuery.value.length === 0) {
        filteredItems.value = [];
        return;
    }

    const { data, error } = await supabase
        .from('students')
        .select(`*`)
        .ilike('nama', `%${searchQuery.value}%`)
        .order('id', { ascending: true });

    if (!error) {
        filteredItems.value = data;
    } else {
        console.error("Error saat fetch nama:", error);
    }
};

// Pantau perubahan input
watch(searchQuery, fetchStudent);

// Pilih barang dari dropdown
const selectStudent = (student) => {
    if (!student) return;
    
    console.log('Siswa dipilih:', student); // Debugging

    selectedItem.value = { 
        id: student.id, 
        student_id: student.id, 
        nama: student.nama,
    };

    searchQuery.value = student.nama
    filteredItems.value = []; 
};

// Kirim data ke Supabase
const submitForm = async () => {
    if (!selectedItem.value || formData.value.status <= 0) {
        console.error("⚠️ Data tidak lengkap!", { selectedItem: selectedItem.value, formData: formData.value });
        return;
    }

    const { error } = await supabase.from('presensi').insert([
        {
            student_id: selectedItem.value.id, 
            status: formData.value.status,
        },
    ]);

    if (error) {
        console.error("Error saat insert ke Supabase:", error);
        return;
    }

    if (!error) navigateTo('/presensi/riwayat')

    // Reset form
    searchQuery.value = '';
    selectedItem.value = null;
    formData.value = { status: '' };
};

definePageMeta({
    layout: 'admin',
    middleware: 'auth'
})

</script>

<template>
    <div class="container-fluid pt-4 mb-5">
        
        <div class="row">
            <div class="col-md-1 mt-2">
                <nuxt-link to="/dashboard" style="text-decoration: none; color: black;">
                    <i class="bi bi-arrow-left-circle fs-2"></i>
                </nuxt-link>
            </div>
            <div class="col-md-10">
                <h2 class="mt-3 head-tittle">Kembali</h2>
            </div>
        </div>

        <!--contact-->
        <div class="row contact">
            <div class="col p-5">
                <div class="card rounded-3">
                    <div class="row justify-content-center">
                        <div class="col-md-5 p-5">
                            <div class="d-flex p-3">
                                
                                    <img src="../../assets/logo1.png" alt="" style="width: 8rem;">
                                    <h3 class="mt-5">Daftar Siswa PKL</h3>
                                <!-- <h2>Hubungi Kami</h2>
                            <h6 class="mt-3">Melayani pertanyaan dan permasalahan customer 24jam</h6> -->
                            </div>
                            <form @submit.prevent="submitForm" class="p-3">
                                <div class="mb-3">
                                    <label class="form-label">Nama Barang</label>
                                    <input v-model="searchQuery" type="text" class="form-control" @focus="fetchStudent"
                                        @input="fetchStudent">
                                    <!-- Dropdown Hasil Pencarian -->
                                    <ul v-if="filteredItems.length > 0 && searchQuery !== selectedItem?.nama"
                                        class="dropdown">
                                        <li v-for="student in filteredItems" :key="student.id"
                                            @click="selectStudent(student)">
                                            {{ student.nama }}
                                        </li>
                                    </ul>
                                </div>
                                <div class="mb-3">
                                    <div class="row">
                                        <label for="exampleInputEmail1" class="form-label" autocomplete="off">Status</label>
                                        <select v-model="formData.status" class="form-control form-control-lg form-select tounded-5 mb-2">
                                            <option disabled value="">Status</option>
                                            <option value="H">H</option>
                                            <option value="I">I</option>
                                            <option value="S">S</option>
                                            <option value="A">A</option>
                                        </select>
                                    </div>
                                </div>
                                <div class="text-center">
                                    
                                        <button type="submit" class="btn mt-4 rounded-5">Tambah</button>
                                </div>
                            </form>
                        </div>
                        
                        <div class="col-md-5">
                            <div class="card card-form">
                                <div class="card-body">
                                    
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Junge&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Kavoon&family=Miltonian+Tattoo&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Red+Rose:wght@300..700&display=swap');


h2, h5, h6, label, .btn, .contact h2 {
    font-family: "Poppins", sans-serif;
}

.card-body {
  background: url('~/assets/background.jpg') no-repeat center center;
  background-size: cover;
  height: 770px;
  
}

.btn {
    width: 100px;
    font-size: 17px;
    color: rgb(8, 8, 8);
    background-color: #BFDEEB;
}

i {
    margin-left: 50px;
}

textarea {
    height: 100px;
}

input, textarea, .card-form {
    border: 1px solid #BFDEEB;
}

.card {
    border: none;
}


@media only screen and (min-width: 600px) and (max-width: 890px) {
    .head-tittle {
        margin-left: 30px;
    }

    .card-body {
        height: 670px;
    }
}

@media only screen and (max-width: 600px) {
    i {
        margin-left: 0;
    }

    .contact {
        font-size: small;
    }

    .card-body {        
        height: 450px;
    }

}
</style>