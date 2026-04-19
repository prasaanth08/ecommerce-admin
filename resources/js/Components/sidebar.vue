<script setup>
import { ref } from 'vue';
import { Link, usePage } from '@inertiajs/vue3';
const page = usePage();
const sidebarOpen = ref(false);
</script>
<template>
    <div 
            v-if="sidebarOpen" 
            class="fixed inset-0 bg-black bg-opacity-50 z-40 lg:hidden"
            @click="sidebarOpen = false"
        ></div>
        <div 
            class="fixed inset-y-0 left-0 w-64 bg-gray-800 text-white p-4 transform z-50
                   transition-transform duration-300
                   lg:translate-x-0 lg:static lg:inset-0"
            :class="sidebarOpen ? 'translate-x-0' : '-translate-x-full'"
        >
            <h2 class="text-xl font-bold mb-6">Admin</h2>
            <ul>
                <li class="mb-2">
                    <Link 
                        href="/dashboard" 
                        class="block p-2 rounded"
                        :class="page.url === '/dashboard' ? 'bg-gray-700' : 'hover:bg-gray-700'"
                        @click="sidebarOpen = false"
                    >
                        Dashboard
                    </Link>
                </li>

                <li class="mb-2">
                    <Link 
                        href="/products" 
                        class="block p-2 rounded"
                        :class="page.url.startsWith('/products') ? 'bg-gray-700' : 'hover:bg-gray-700'"
                        @click="sidebarOpen = false"
                    >
                        Products
                    </Link>
                </li>
            </ul>
        </div>
</template>
<script>

export default {
    name:'sidebar'
}
    
</script>