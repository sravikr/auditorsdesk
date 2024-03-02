<template>
 
      <!-- Iterate through the menuItems array -->
      <li v-for="menuItem in menuItems" :key="menuItem.id" class="sidebar-menu__item">
        <router-link :to="menuItem.route" class="sidebar-menu__link">
          <span v-if="menuItem.icon" class="material-icons-outlined sidebar-menu__icons">{{ menuItem.icon }}</span>
    <component v-else-if="menuItem.svg" :is="menuItem.svg" class="sidebar-menu__icons"></component>
   
          {{ menuItem.label }}
        </router-link>
      </li>
 
</template>

<script setup>
import IconAnalysisVue from './icons/IconAnalysis.vue';

// Define an array of menu items
const menuItems = [
  { id: 1, label: 'Home', route: '/dashboard', icon: 'visibility' },
  { id: 2, label: 'Analysis', route: '/home', icon:"analysis"  },
  { id: 3, label: 'Stakeholders', route: '/home', icon: 'chart' },
  { id: 4, label: 'Compliances', route: '/home', icon: 'chart' },
  { id: 5, label: 'Observations', route: '/Observation', icon: 'chart' },
  { id: 6, label: 'Feedback', route: '/home', icon: 'chart' },
  { id: 7, label: 'Support', route: '/support', icon: 'chart' },
  
  
  // Add more menu items as needed
];
</script>

 