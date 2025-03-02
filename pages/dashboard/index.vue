<script setup>
definePageMeta({
    layout: 'admin',
    middleware: 'auth'
})

</script>

<template>
    <div class="container">
        <div class="card mt-5 mb-5">
            <div class="row mt-5">
                <div class="col-1 icon-data mt-4">
                    <i class="bi bi-people fs-1"></i>
                </div>
                <div class="col-5">
                    <nuxt-link to="/data/form1" class="no-underline"><h2><b>Catatan Data PKL</b></h2></nuxt-link>
                </div>
            </div>
        </div>
        <div class="card mt-5">
            <div class="row mt-5">
                <div class="col-1 icon mt-4">
                    <i class="bi bi-people fs-1"></i>
                </div>
                <div class="col-4 text">
                    <nuxt-link to="/presensi/" class="no-underline"><h2><b>Presensi PKL</b></h2></nuxt-link>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inria+Serif:ital,wght@0,300;0,400;0,700;1,300;1,400;1,700&display=swap');

.card{
    background-color: #DEEAEF;
    width: 90%;
    height: 200px;
    margin-left: 60px;
    /* padding-left: 50px; */
}

.icon{
    margin-left: 100px;
    
}

.icon-data{
    margin-left: 120px;
}
.row{
    justify-content: center;
}

/* .text{
    text-align: center;
} */

h2{
    font-family: "Inria Serif", serif;
    font-weight: 300;
    font-style: normal;
    color: rgb(22, 22, 22);
    text-decoration: none;
    padding-top: 30px;
}

.no-underline {
  text-decoration: none;
}
</style>

