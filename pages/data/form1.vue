<script setup>
const supabase = useSupabaseClient()
const form = ref({
    nama: "",
    nomor_telpon: "",
    sekolah: "",
    jurusan: "",
    tanggal_awal: null,
    tanggal_akhir: null,
    penempatan: ""
})

const kirimData = async () => {
    const { error } = await supabase.from('students').insert([form.value])
    console.log(error)
    if(!error) navigateTo('/data/riwayat')
}

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
                <div class="card rounded-3 ">
                    <div class="row justify-content-center mt-5">
                        <div class="col-md-5 p-5">
                            <div class="d-flex p-3">
                                
                                    <img src="../../assets/logo1.png" alt="" style="width: 8rem;">
                                    <h3 class="mt-5">Daftar Siswa PKL</h3>
                                <!-- <h2>Hubungi Kami</h2>
                            <h6 class="mt-3">Melayani pertanyaan dan permasalahan customer 24jam</h6> -->
                            </div>
                            <form @submit.prevent="kirimData" class="p-3">
                                <div class=" form-group mb-3">
                                    <label for="exampleInputName" class="form-label">Nama</label>
                                    <input v-model="form.nama" type="text" class="form-control form-control-lg rounded-5" />
                                </div>
                                <div class=" form-group mb-3">
                                    <label for="exampleInputName" class="form-label">Nomor Telepon</label>
                                    <input v-model="form.nomor_telpon" type="text" class="form-control form-control-lg rounded-5" />
                                </div>
                                <div class=" form-group mb-3">
                                    <label for="exampleInputName" class="form-label">Jurusan</label>
                                    <input v-model="form.jurusan" type="text" class="form-control form-control-lg rounded-5" />
                                </div>
                                <div class=" form-group mb-3">
                                    <label for="exampleInputName" class="form-label">Sekolah</label>
                                    <input v-model="form.sekolah" type="text" class="form-control form-control-lg rounded-5" />
                                </div>
                                <div class=" form-group mb-3">
                                    <label for="exampleInputName" class="form-label">Awal PKL</label>
                                    <input v-model="form.tanggal_awal" type="date" class="form-control form-control-lg rounded-5" />
                                </div>
                                <div class=" form-group mb-3">
                                    <label for="exampleInputName" class="form-label">Akhir PKL</label>
                                    <input v-model="form.tanggal_akhir" type="date" class="form-control form-control-lg rounded-5" />
                                </div>
                                <div class=" form-group mb-3">
                                    <label for="exampleInputName" class="form-label">Penempatan</label>
                                    <input v-model="form.penempatan" type="text" class="form-control form-control-lg rounded-5" />
                                </div>
                                <div class="text-center">
                                    
                                        <button type="submit" class="btn mt-4 rounded-5">Tambah</button>
                                </div>
                            </form>
                        </div>
                        <div class="col-md-5 mb-5">
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
  height: 900px;
  
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
    border: 1px solid #BFDEEB;
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