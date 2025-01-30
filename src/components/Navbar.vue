<template>
  <header class="bg-blue-600 text-white p-4 flex items-center justify-between">
    <button @click="toggleDrawer" class="text-white focus:outline-none">
      &#9776;
    </button>
    <h1 class="text-lg font-semibold">My Website</h1>
    <nav class="hidden md:flex space-x-4">
      <button v-for="(item, index) in navItems" :key="index" class="hover:underline">
        {{ item }}
      </button>
    </nav>
  </header>
  
  <div v-if="drawerOpen" class="fixed inset-0 bg-gray-800 bg-opacity-50 z-50" @click="toggleDrawer"></div>
  
  <aside :class="{'translate-x-0': drawerOpen, '-translate-x-full': !drawerOpen}"
         class="fixed top-0 left-0 w-64 h-full bg-white shadow-lg transform transition-transform duration-300 ease-in-out z-50">
    <button @click="toggleDrawer" class="block p-4 text-right text-gray-700">&times;</button>
    <ul class="p-4 space-y-4">
      <li v-for="(item, index) in navItems" :key="index">
        <button @click="toggleDrawer" class="w-full text-left p-2 hover:bg-gray-200">
          {{ item }}
        </button>
      </li>
    </ul>
  </aside>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const drawerOpen = ref(false);
    const navItems = ref(['Home', 'About', 'Contact']);

    const toggleDrawer = () => {
      drawerOpen.value = !drawerOpen.value;
    };

    return { drawerOpen, navItems, toggleDrawer };
  }
};
</script>

<style>
/* Tambahan untuk animasi menu */
</style>
