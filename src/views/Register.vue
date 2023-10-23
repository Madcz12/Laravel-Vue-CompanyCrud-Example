<script setup>
import { ref } from 'vue';
import { useAuthStore } from '../stores/auth';
const authStore = useAuthStore();
const form = ref({ name: '', email: '', password: '' });

</script>

<template>
    <div class="row">
        <div class="col">
            <div class="card border border-success">
                <div class="card-header bg-sucess border border-success text-black">REGISTER</div>
                <div class="card-body">
                    <form @submit.prevent="authStore.register(form)">
                        <div class="input-group mb-3">
                            <span class="input-group-text">
                                <i class="fa-solid fa-user"></i>
                            </span>
                            <input autofocus type="text" v-model="form.name" placeholder="name" class="form-control">
                        </div>
                        <div class="input-group mb-3">
                            <span class="input-group-text">
                                <i class="fa-solid fa-at"></i>
                            </span>
                            <input autofocus type="email" v-model="form.email" placeholder="email" class="form-control">
                        </div>
                        <div class="input-group mb-3">
                            <span class="input-group-text">
                                <i class="fa fa-key" aria-hidden="true"></i>
                            </span>
                            <input type="password" v-model="form.password" placeholder="password" class="form-control">
                        </div>
                        <div class="d-grid col-10 mx-auto">
                            <button class="btn btn-dark">Send</button>
                        </div>

                    </form>
                </div>
            </div>
        </div>
    </div>
</template>