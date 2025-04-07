<script setup>
const supabase = useSupabaseClient()
const presensi = ref ([])
const keyword = ref('')

const getPresensi = async () => {
  const { data, error } = await supabase.from("presensi").select(`*, students(*)`).order('id', { ascending: false })
  if(data) presensi.value = data
}

const filterPresensi = computed(() => {
    return presensi.value.filter((item) => {
        return (
            item.students?.nama?.toLowerCase().includes(keyword.value.toLowerCase()) ||
            item.tanggal?.toLowerCase().includes(keyword.value.toLowerCase())
        )
    })
})

onMounted(() => getPresensi())


definePageMeta({
    layout: 'admin',
    middleware: 'auth'
})
</script>

<template>
    <div class="container">
        <div class="d-flex gap-4 mt-5 mb-4 float-end">
            <form @submit.prevent="filterPresensi" class="input-group flex-nowrap rounded w-100 h-100 d-flex gap-4">
              <input v-model="keyword" type="search" class="form-control" placeholder="Search" aria-label="Search"
                aria-describedby="search-addon" />
                <input v-model="keyword" type="date">
            </form>
            <nuxt-link to="/presensi">
                <div class="btn  float-end mb-2">
                    <i class="bi bi-plus-circle fs-4"></i>
                </div>
            </nuxt-link> 
        </div>
        <table class="table mt-5">
            <thead class="thead-dark title">
                <tr>
                    <th>Nomor</th>
                    <th>Tanggal</th>
                    <th>Nama</th>
                    <th>Sekolah</th>
                    <th>Status</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(absen, i) in filterPresensi" :key="i">
                    <td>{{ i + 1 }}</td>
                    <td>{{ absen.tanggal }}</td>
                    <td>{{ absen.students.nama }}</td>
                    <td>{{ absen.students.sekolah }}</td>
                    <td>{{ absen.status }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<style scoped>

.title{
    background-color: #BFDEEB;
}

.btn{
    background-color: #BFDEEB;
}
</style>