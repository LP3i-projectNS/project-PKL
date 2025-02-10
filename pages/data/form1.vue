<template>
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
                            <nuxt-link to="/data/riwayat/"><button id="submit-btn" class="rounded-2 shadow">KIRIM</button></nuxt-link>
                        </div>
                    </div>
                    <div class="col-md-6">
                        <div class="card">
                            <div class="card-body">
                                
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>

<style scoped>

</style>