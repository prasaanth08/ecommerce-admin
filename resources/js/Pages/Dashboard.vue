<script setup>
import { Head } from '@inertiajs/vue3'
import AdminLayout from '@/Layouts/AdminLayout.vue'
import Chart from '@/Components/Chart.vue'
</script>

<template>
    <Head title="Dashboard" />

    <AdminLayout>
        <h2 class="text-2xl font-bold mb-6">Dashboard</h2>

        <!-- STATS -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mb-6">
            <div class="bg-white p-4 shadow rounded">
                <h3 class="text-gray-500">Total Products</h3>
                <p class="text-2xl font-bold">120</p>
            </div>

            <div class="bg-white p-4 shadow rounded">
                <h3 class="text-gray-500">Total Orders</h3>
                <p class="text-2xl font-bold">340</p>
            </div>

            <div class="bg-white p-4 shadow rounded">
                <h3 class="text-gray-500">Total Users</h3>
                <p class="text-2xl font-bold">89</p>
            </div>
        </div>

        <!-- CHART -->
        <div class="bg-white p-4 shadow rounded">
            <h3 class="mb-4 font-semibold">Orders Overview</h3>
            <Chart />
        </div>
    </AdminLayout>
</template>