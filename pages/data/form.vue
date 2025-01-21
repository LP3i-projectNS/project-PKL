<template>
    <div class="container">
        <div class="card mt-5">
            <img src=".././../assets/logo1.png" alt="" class="logo mt-4">
            <h2 class="mt-2"><b>DAFTAR PKL</b></h2>
            <p>LP3i Kota Tasikmalaya</p>
            <div class=" form-group mb-3">
                <label for="exampleInputName" class="form-label">Nama</label>
                <input type="text" class="form-control form-control-lg rounded-5" />
            </div>
            <div class=" form-group mb-3">
                <label for="exampleInputName" class="form-label">Nama</label>
                <input type="text" class="form-control form-control-lg rounded-5" />
            </div>
            <div class=" form-group mb-3">
                <label for="exampleInputName" class="form-label">Nama</label>
                <input type="text" class="form-control form-control-lg rounded-5" />
            </div>
            <button id="submit-btn">KIRIM</button>
        </div>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inria+Serif:ital,wght@0,300;0,400;0,700;1,300;1,400;1,700&family=Judson:ital,wght@0,400;0,700;1,400&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Inria+Serif:ital,wght@0,300;0,400;0,700;1,300;1,400;1,700&display=swap');


.card{
    width: 500px;
    height: 400px;
    margin-left: 270px;
    border: 3px solid #7f898b;
    /* justify-content: center; */
}

h2{
    font-family: "Inria Serif", serif;
    font-weight: 300;
    font-style: normal;
    font-weight: bold;
    margin-left: 150px;
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