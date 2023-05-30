<script setup>
import { Head } from '@inertiajs/vue3';
import Banner from '@/Components/Banner.vue';
import GuestNavbar from "@/Components/_includes/GuestNavbar.vue";
import GuestFooter from "@/Components/_includes/GuestFooter.vue";

defineProps({
    title: String,
});

</script>

<template>
    <Head :title="title" />

    <Banner />
    
    <div class="body dark:bg-[#17202A] dark:text-[#94A2B8]">
        <!-- Navigation -->
        <GuestNavbar />

        <!-- Page Content -->
        <main class="content">
            <slot />
        </main>

        <!-- Footer -->
        <GuestFooter />
    </div>
</template>
