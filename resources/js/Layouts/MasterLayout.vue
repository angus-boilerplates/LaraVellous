<script setup>
import { Head } from '@inertiajs/vue3';
import Banner from '@/Components/Banner.vue';

defineProps({
    title: String,
});

</script>

<template>
    <Head :title="title" />

    <Banner />

    <div class="body bg-gray-100 text-slate-700 dark:bg-[#17202A] dark:text-[#94A2B8]">
        <slot />
    </div>
</template>
