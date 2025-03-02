<template>
    <div class="container-fluid p-0">

        <div class="text-center p-5">
            <h2>Silahkan login, <b>Admin</b></h2>
        </div>

        <div class="row justify-content-center">
            <div class="col-8 col-md-7 col-lg-4">
                <div class="card rounded-4 shadow">
                    <div class="card-body m-3">
                        <form @submit.prevent="SignIn">
                            <div class="mb-3">
                                <label for="exampleInputEmail1" class="form-label">Email</label>
                                <input v-model="email" type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
                            </div>
                            <div class="mb-3">
                                <label for="exampleInputPassword1" class="form-label">Password</label>
                                <input v-model="password" type="password" class="form-control" id="exampleInputPassword1">
                            </div>
                            <p v-if="errorMessage">{{ errorMessage }}</p>
                            <div class="text-center mt-5">
                                <button type="submit" class="btn rounded-5">Login</button>
                            </div>
                        </form> 
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>

const supabase = useSupabaseClient()
const email = ref ("")
const password = ref ("")
const errorMessage = ref("")

async function SignIn() {
  const { data, error } = await supabase.auth.signInWithPassword({
    email: email.value,
    password: password.value,
  })
  if (error) {
    errorMessage.value = "Email atau password salah"
  }
  if (data) {
    navigateTo ("/dashboard")
  }
}

// definePageMeta ({
//     layout: 'login'
// })

</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Kavoon&family=Miltonian+Tattoo&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Red+Rose:wght@300..700&display=swap');

.container-fluid {
    background-color: #D8C7A6;
    height: 100vh;
}


.text-center, label {
    font-family: "Poppins", sans-serif;
}

.btn {
    width: 125px;
    color: white;
    background-color: #C6AC7B;
}

@media only screen and (max-width: 600px) {
    .btn {
        width: 100px;
    }

    .text-center, label {
        font-size: small;
    }
}

</style>