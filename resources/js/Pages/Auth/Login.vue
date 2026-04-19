<script setup>
import Checkbox from '@/Components/Checkbox.vue';
import GuestLayout from '@/Layouts/GuestLayout.vue';
import InputError from '@/Components/InputError.vue';
import InputLabel from '@/Components/InputLabel.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import TextInput from '@/Components/TextInput.vue';
import { Head, Link, useForm } from '@inertiajs/vue3';

defineProps({
    canResetPassword: {
        type: Boolean,
    },
    status: {
        type: String,
    },
});

const form = useForm({
    email: '',
    password: '',
    remember: false,
});

const submit = () => {
    form.post(route('login'), {
        onFinish: () => form.reset('password'),
    });
};
</script>

<template>
 <!-- <GuestLayout> -->
        <Head title="Login" />

        <div class="min-h-screen flex">
            <div class="hidden lg:flex w-1/2 bg-indigo-600 text-white items-center justify-center">
                <div class="text-center px-10">
                    <h1 class="text-4xl font-bold mb-4">Welcome Back 👋</h1>
                    <p class="text-lg opacity-90">
                        Manage your ecommerce admin panel easily and efficiently.
                    </p>
                </div>
            </div>
            <div class="flex w-full lg:w-1/2 items-center justify-center bg-gray-100">
                <div class="w-full max-w-md bg-white p-8 rounded-2xl shadow">

                    <h2 class="text-2xl font-bold text-center mb-6">Login</h2>

                    <div v-if="status" class="mb-4 text-sm text-green-600 text-center">
                        {{ status }}
                    </div>

                    <form @submit.prevent="submit">
                        <div>
                            <InputLabel for="email" value="Email" />
                            <TextInput
                                id="email"
                                type="email"
                                class="mt-1 block w-full"
                                v-model="form.email"
                                required
                                autofocus
                            />
                            <InputError class="mt-2" :message="form.errors.email" />
                        </div>
                        <div class="mt-4">
                            <InputLabel for="password" value="Password" />
                            <TextInput
                                id="password"
                                type="password"
                                class="mt-1 block w-full"
                                v-model="form.password"
                                required
                            />
                            <InputError class="mt-2" :message="form.errors.password" />
                        </div>
                        <div class="mt-4 flex items-center justify-between">
                            <label class="flex items-center">
                                <Checkbox name="remember" v-model:checked="form.remember" />
                                <span class="ms-2 text-sm text-gray-600">Remember me</span>
                            </label>

                            <Link
                                v-if="canResetPassword"
                                :href="route('password.request')"
                                class="text-sm text-indigo-600 hover:underline"
                            >
                                Forgot?
                            </Link>
                        </div>
                        <div class="mt-6">
                            <PrimaryButton
                                class="w-full justify-center"
                                :class="{ 'opacity-25': form.processing }"
                                :disabled="form.processing"
                            >
                                Log in
                            </PrimaryButton>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    <!-- </GuestLayout> -->
</template>
