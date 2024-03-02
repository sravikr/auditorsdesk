<script setup>
import IconAnalysis from '../components/icons/IconAnalysis.vue'
import { onMounted } from 'vue';

const props = defineProps(['dashboardNumber', 'dashboardSubTitle',
'dashboardTrendFigure', 'svgIcon', 'dashboardChart']);
</script>

<template>
  
  <div class="dashboard-card">
    <span class="dashboard-card__icon" >
      <img src="../assets/icon-profit.svg" alt="icon-profit" />
    </span>
    <div class="dashboard-card__data">
      <span>{{ dashboardSubTitle }}</span>
      <strong>{{ dashboardNumber }}</strong>
      <strong>{{ dashboardTrendFigure }}</strong>

    </div>
    <span class="dashboard-card__chart">
      <img src="../assets/chart-revenue.svg" alt="icon" />
    </span>
  </div>
</template>
