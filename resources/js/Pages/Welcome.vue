<script setup>
import { Head, Link } from '@inertiajs/inertia-vue3';
import GuestLayout from "@/Layouts/GuestLayout.vue";

defineProps({
    canLogin: Boolean,
    canRegister: Boolean,
    laravelVersion: String,
    phpVersion: String,
});
</script>

<template>
    <Head title="Tailwind CSS Komponentleri" />
  <guest-layout>

  </guest-layout>
</template>
