<script setup>
import IconAnalysis from '../components/icons/IconAnalysis.vue'
import { onMounted } from 'vue';
import overview from '../pages/overview/overview.vue'
import SidebarMenu from '../components/SideBarMenu.vue';
const props = defineProps(['title', 'otherText']);
</script>

<template>
  
  <section class="section-title">
    <h4>{{ title }}<span>{{ otherText }}</span></h4>
  </section>
</template>
