<script setup>
const supabase = useSupabaseClient()
const students = ref ([])
const keyword = ref('')

const getStudent = async () => {
  const { data, error } = await supabase.from("students").select(`*`).order('id', { ascending: false })
  .ilike('nama',`%${keyword.value}%`)
  if(data) students.value = data
}

const studentFiltered = computed(() => {
  return students.value.filter((s) => {
    return (
      s.nama?.toLowerCase().includes(keyword.value.toLowerCase()) ||
      s.sekolah?.toLowerCase().includes(keyword.value.toLowerCase())
    )
  })
})

onMounted(() => getStudent())


definePageMeta({
    layout: 'admin',
    middleware: 'auth'
})
</script>

<template>
    <div class="container">
        <div class="d-flex gap-4 mt-5 mb-4 float-end">
            <form @submit.prevent="getStudent" class="input-group flex-nowrap rounded w-100 h-100">
              <input v-model="keyword" type="search" class="form-control" placeholder="Search" aria-label="Search"
                aria-describedby="search-addon" />
              <span class="input-group-text"><i class="bi bi-search"></i></span>
            </form>
            <nuxt-link to="/data/form1">
                <div class="btn  float-end mb-2">
                    <i class="bi bi-plus-circle fs-4"></i>
                </div>
            </nuxt-link> 
        </div>
        <table class="table mt-5">
            <thead class="thead-dark title">
                <tr>
                    <th>No</th>
                    <th>Nama</th>
                    <th>Nomor Telepon</th>
                    <th>Sekolah</th>
                    <th>Jurusan</th>
                    <th>Awal PKL</th>
                    <th>Akhir PKL</th>
                    <th>Penempatan</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(student, i) in studentFiltered" :key="i">
                    <td>{{ i + 1 }}</td>
                    <td>{{ student.nama }}</td>
                    <td>{{ student.nomor_telpon }}</td>
                    <td>{{ student.sekolah }}</td>
                    <td>{{ student.jurusan }}</td>
                    <td>{{ student.tanggal_awal }}</td>
                    <td>{{ student.tanggal_akhir }}</td>
                    <td>{{ student.penempatan }}</td>
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