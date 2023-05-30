<script setup>
import { Head, Link } from '@inertiajs/vue3';
import GuestLayout from "@/Layouts/GuestLayout.vue";
import PageContainer from "@/Components/PageContainer.vue";

defineProps({
    canLogin: Boolean,
    canRegister: Boolean,
    laravelVersion: String,
    phpVersion: String,
});
</script>

<template>
    <GuestLayout title="Home">
        <PageContainer>
            <p>Welcome buddy</p>
        </PageContainer>
    </GuestLayout>
</template>

