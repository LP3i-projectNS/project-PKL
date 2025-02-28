<template>
        <div class="card rounded-3 ">
            <div class="form cover p-0 rounded-3">
                <div class="card-form rounded-2" >
                    
                        <div class="row d-flex justify-content-center" style="width: 120%; right: 0">
                            <div class="col-lg-2">
                                <img src="../../assets/logo1.png" alt="" style="width: 100px;" class="img"/>
                            </div>
                            <div class="col-lg-4 d-flex align-items-center flex-column pt-3 text-start">
                                <h3>DAFTAR PKL</h3>
                            </div>
                        </div>
                    
                    <div class="p-3">
                            <div class=" form-group mb-3">
                                <label for="exampleInputName" class="form-label">Nama</label>
                                <input type="text" class="form-control rounded-4 " />
                            </div>
                            <div class=" form-group mb-3">
                                <label for="exampleInputName" class="form-label">Jurusan</label>
                                <input type="text" class="form-control rounded-5" />
                            </div>
                            <div class=" form-group mb-3">
                                <label for="exampleInputName" class="form-label">Sekolah</label>
                                <input type="text" class="form-control rounded-5" />
                            </div>
                            <div class=" form-group mb-3">
                                <label for="exampleInputName" class="form-label">Awal PKL</label>
                                <input type="date" class="form-control rounded-5" />
                            </div>
                            <div class=" form-group mb-3">
                                <label for="exampleInputName" class="form-label">Akhir PKL</label>
                                <input type="date" class="form-control rounded-5" />
                            </div>
                            <nuxt-link to="/data/riwayat/"><button id="submit-btn" class="btn rounded-2 shadow">KIRIM</button></nuxt-link>
                        </div>
                </div>
            </div>
        </div>

</template>

<style scoped>


.card-form{
    margin-left: 560px;
    background-color: white;
    width: 50%;
}

.card{
    background-color: black;
    margin-top: 70px;
}

.row{
    text-align: center;
}
.cover{
    background: url('../../assets/bg.jpg') no-repeat center center;
    background-size: cover;
    height: 500px;
    width: 1115px;
    max-width: 2000px;
}

.btn{
    background-color: #BFDEEB;
    margin-left: 450px;
}

</style>

<!-- <template>
    <div class="row contact">
        <div class="col p-5">
            <div class="card rounded-3">
                <div class="row">
                    <div class="col-md-6 p-5">
                        <div class="p-3">
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
                            <nuxt-link to="/data/riwayat/"><button id="submit-btn" class="btn rounded-2 shadow">KIRIM</button></nuxt-link>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </div>

</template>

<style scoped>

.btn{
    background-color: #BFDEEB;
    margin-left: 250px;
}
</style> -->