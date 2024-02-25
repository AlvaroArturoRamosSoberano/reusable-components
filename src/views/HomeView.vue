<script setup>
import Sidebar from "@/components/sidebar/Sidebar.vue";
import { ref } from 'vue';

const currentIcon = ref('caret-back-outline');

const toggleIcon = (newIcon) => {
  currentIcon.value = newIcon;
};
</script>

<template>
  <section>
    <div class="h-screen w-screen bg-slate-300">
      <sidebar title="SideBar" :icon="currentIcon" @change-icon="toggleIcon"></sidebar>
    </div>
  </section>
</template>
