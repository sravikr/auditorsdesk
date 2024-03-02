<script setup>
import IconAnalysis from '../components/icons/IconAnalysis.vue'
import { onMounted } from 'vue';
import SidebarMenu from '../components/SideBarMenu.vue';

let headerHeight = 0; // Initialize with a default value

onMounted(() => {
  // Access the header element after the component is mounted
  const header = document.querySelector(".site-header");
  if (header) {
    headerHeight = header.clientHeight;

    // Access the sidebar element and set the top property
    const sidebar = document.querySelector(".sidebar-menu");
    if (sidebar) {
      sidebar.style.top = `${headerHeight + 6}px`; 
    }
    
  }
});

// sidebar.style.top = header.clientHeight

</script>

<template>
  
  <div class="sidebar-menu">
    <ul>
      
      <li class="d-flex sidebar-menu__redirect">
        <span class="material-icons-outlined pe-1">
          reply
          </span>
        <a href="">
          Back to <br />Dashboard
        </a>
      </li>
      <SidebarMenu />

    </ul>
  </div>
</template>
