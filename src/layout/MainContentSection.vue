<script setup>
import IconAnalysis from '../components/icons/IconAnalysis.vue'
import { onMounted, ref } from 'vue';
// import overview from '../pages/overview/overview.vue'
import SidebarMenu from '../components/SideBarMenu.vue';

let headerHeight = 0; // Initialize with a default value


onMounted(() => {
  const header = document.querySelector(".site-header");
  if (header) {
    headerHeight = header.clientHeight;

    // Access the sidebar element and set the top property
    const sidebar = document.querySelector(".sidebar-menu");
    const mainContentSection = document.querySelector(".main-content-sec");
    if(mainContentSection) {
      mainContentSection.style.marginLeft = `${sidebar.clientWidth}px`;
    }
    if (sidebar) {
      sidebar.style.top = `${headerHeight + 2}px`;
    }
    
  }
});
</script>

<template>
  
  <div class="main-content-sec">
    <router-view></router-view>
  </div>
</template>
