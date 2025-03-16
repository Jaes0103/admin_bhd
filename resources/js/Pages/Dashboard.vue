<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
import Sidebar from '@/Components/Sidebar.vue';
import Footer from '@/Components/Footer.vue'
</script>

<template>
    <Head title="Dashboard" />
    <div class="min-h-screen flex">
        <Sidebar :isOpen="isSidebarOpen" />
        <div class="flex-grow flex flex-col">
        <main class="flex-grow">
        <!--main content-->
        </main>
      <Footer />
    </div>
    </div>

</template>

<style scoped>
footer {
  background-color: #2d3748; 
  color: #ffffff; 
  padding: 1rem; 
  text-align: center;
}
</style>
