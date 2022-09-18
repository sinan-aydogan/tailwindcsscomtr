<script setup>
import {ref} from 'vue';
import {Head, Link} from '@inertiajs/inertia-vue3';
import ApplicationMark from '@/Components/ApplicationMark.vue';
import Banner from '@/Components/Banner.vue';
import Dropdown from '@/Components/Dropdown.vue';
import DropdownLink from '@/Components/DropdownLink.vue';
import NavLink from '@/Components/NavLink.vue';
import ResponsiveNavLink from '@/Components/ResponsiveNavLink.vue';

defineProps({
  title: String,
});

const showingNavigationDropdown = ref(false);

const menuToggle = () => {
  showingNavigationDropdown.value = !showingNavigationDropdown.value
}
</script>

<template>
  <div>
    <Head :title="title"/>

    <Banner/>

    <div class="min-h-screen px-4">
      <nav class="max-w-7xl bg-white border-b border-gray-100 mx-auto">
        <!-- Primary Navigation Menu -->
        <div class="max-w-7xl mx-auto">
          <div class="flex justify-between h-20">
            <!--Left Side-->
            <div class="flex items-center">
              <!-- Logo -->
              <Link :href="route('home')" class="shrink-0 flex items-center space-x-2">
                <span class="text-2xl font-bold text-cyan-500">tailwindcss</span>
                <div class="flex flex-col leading-none border-l pl-2 text-xs text-cyan-500 border-slate-300">
                  <span>com</span>
                  <span>tr</span>
                </div>
              </Link>
            </div>
            <!--Right Side-->
            <div class="flex items-center space-x-4">
              <!-- Navigation Links -->
              <div class="hidden space-x-8 sm:-my-px sm:ml-10 sm:flex">
                <!--Komponentler-->
                <NavLink :href="route('components')" :active="route().current('components')">
                  Komponentler
                </NavLink>

                <!--Temalar-->
                <NavLink :href="route('themes')" :active="route().current('themes')">
                  Temalar
                </NavLink>

                <!--Dökümantasyon-->
                <NavLink :href="route('documentation')" :active="route().current('documentation')">
                  Dökümantasyon
                </NavLink>
              </div>

              <!--Hamburger Menu-->
              <svg @click="menuToggle" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                   stroke-width="1.5"
                   stroke="currentColor"
                   class="w-7 h-7 flex sm:hidden cursor-pointer"
              >
                <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"/>
              </svg>
            </div>
          </div>
        </div>

        <!-- Responsive Navigation Menu -->
        <div class="fixed top-0 right-0 flex flex-col sm:hidden bg-white shadow-lg border-l h-screen transition-all duration-500" :class="{'mr-0': showingNavigationDropdown, '-mr-64': ! showingNavigationDropdown}">
          <div class="flex items-center justify-end h-16 border-b pr-4">
            <svg @click="menuToggle" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-7 h-7 cursor-pointer">
              <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </div>

          <div class="flex w-64 pt-2 pb-3 space-y-1">
            <ResponsiveNavLink :href="route('home')" :active="route().current('home')">
              Komponentler
            </ResponsiveNavLink>
          </div>
        </div>
      </nav>

      <!-- Page Heading -->
      <header v-if="$slots.header" class="bg-white shadow">
        <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
          <slot name="header"/>
        </div>
      </header>

      <!-- Page Content -->
      <main class="max-w-7xl mx-auto py-12">
        <slot/>
      </main>
    </div>
  </div>
</template>

<style scoped>
</style>
