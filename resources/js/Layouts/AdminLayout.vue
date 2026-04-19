
<script setup>
import SideBar from '../Components/sidebar.vue'
import Nav from '../Components/nev.vue'
</script>
<template>
    <div class="flex h-screen overflow-hidden">
        <SideBar />

        <div class="flex-1 flex flex-col bg-gray-100">
            <Nav />
            <main class="p-4 flex-1 overflow-y-auto">
                <slot />
            </main>
        </div>
    </div>
</template>

