<script setup>
import { ref } from 'vue';
import { useAuthStore } from '../stores/auth';
const authStore = useAuthStore();
const form = ref({ email: '', password: '' });

</script>

<template>
    <div class="row">
        <div class="col">
            <div class="card border border-success">
                <div class="card-header bg-sucess border border-success text-black">LOGIN</div>
                <div class="card-body">
                    <form @submit.prevent="authStore.login(form)">
                        <div class="input-group mb-3">
                            <span class="input-group-text">
                                <i class="fa-solid fa-at"></i>
                            </span>
                            <input autofocus type="text" v-model="form.email" placeholder="email" class="form-control">
                        </div>
                        <div class="input-group mb-3">
                            <span class="input-group-text">
                                <i class="fa fa-key" aria-hidden="true"></i>
                            </span>
                            <input type="password" v-model="form.password" placeholder="password" class="form-control">
                        </div>
                        <div class="d-grid col-10 mx-auto">
                            <button class="btn btn-dark">Login</button>
                        </div>
                        <RouterLink :to="{ path: 'register' }">Register</RouterLink>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>