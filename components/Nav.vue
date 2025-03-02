<script setup>
const route = useRoute()
const router = useRouter()

const hiddenRoutes = ['login']

const shouldShowNavbar = !hiddenRoutes.includes(route.name)

const isActive = ref('home');

const setActive = (tab) => {
  isActive.value = tab;
};

</script>


<template>
    <div v-if="route?.name != 'login'" class="container-fluid p-0 nav">
        <div class="row justify-content-center m-0" style="background-color: #bfdeeb; width: 100%; right: 0">
        <div class="col-lg-1 col-md-2 col-sm-3 col-3">
            <img src="../assets/logo1.png" alt="" style="width: 100px;" class="img"/>
        </div>
        <div class="col-lg-4 col-md-9 col-sm-10 col-12 d-flex flex-column pt-3 text-start">
            <h4>PRESENSI PKL</h4>
            <address>LP3i KOTA TASIKMALAYA</address>
        </div>
        </div>
    </div>
</template>
  
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Inknut+Antiqua:wght@300;400;500;600;700;800;900&display=swap");
h4 {
  font-family: "Inknut Antiqua", serif;
  font-weight: 400;
  font-style: normal;
  margin-top: 8px;
}

@import url("https://fonts.googleapis.com/css2?family=Inknut+Antiqua:wght@300;400;500;600;700;800;900&family=Inria+Serif:ital,wght@0,300;0,400;0,700;1,300;1,400;1,700&display=swap");
address {
  font-family: "Inria Serif", serif;
  font-weight: 500;
  font-style: normal;
  margin: 0px;
}

</style>

