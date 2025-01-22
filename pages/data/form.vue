<template>
    <div class="container-data">
        <div class="card mt-5">
            <img src=".././../assets/logo1.png" alt="" class="logo mt-4">
            <h2 class="mt-2"><b>DAFTAR PKL</b></h2>
            <p>LP3i Kota Tasikmalaya</p>
            <div class=" form-group mb-3">
                <label for="exampleInputName" class="form-label">Nama</label>
                <input type="text" class="form-control form-control-lg rounded-5" />
            </div>
            <div class=" form-group mb-3">
                <label for="exampleInputName" class="form-label">Jurusan</label>
                <input type="text" class="form-control form-control-lg rounded-5" />
            </div>
            <div class=" form-group mb-3">
                <label for="exampleInputName" class="form-label">Sekolah</label>
                <input type="text" class="form-control form-control-lg rounded-5" />
            </div>
            <div class=" form-group mb-3">
                <label for="exampleInputName" class="form-label">Awal PKL</label>
                <input type="date" class="form-control form-control-lg rounded-5" />
            </div>
            <div class=" form-group mb-3">
                <label for="exampleInputName" class="form-label">Akhir PKL</label>
                <input type="date" class="form-control form-control-lg rounded-5" />
            </div>
            <nuxt-link to="/data/riwayat/"><button id="submit-btn" class="rounded-2 shadow">KIRIM</button></nuxt-link>
            
        </div>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inria+Serif:ital,wght@0,300;0,400;0,700;1,300;1,400;1,700&family=Judson:ital,wght@0,400;0,700;1,400&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Inria+Serif:ital,wght@0,300;0,400;0,700;1,300;1,400;1,700&display=swap');


.card{
    width: 500px;
    height: 750px;
    margin-left: 300px;
    border: 3px solid #7f898b;
    align-content: center;
    /* justify-content: center; */
}

h2{
    font-family: "Inria Serif", serif;
    font-weight: 300;
    font-style: normal;
    font-weight: bold;
    margin-left: 150px;
}

.btn{
    width: 45px;
    background-color: #7f898b;
}

.form-group{
    padding-left: 10px;
}

.form-control{
    width: 450px;
    margin-left: 10px;
    height: 10px;
}

p{
    font-family: "Inria Serif", serif;
    font-weight: 300;
    font-style: normal;
    font-weight: bold;
    margin-left: 160px;
    font-size: 15px;
}
.logo{
    width: 100px;
    margin-left: 190px;
}
</style>