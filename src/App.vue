<script setup>
import HelloWorld from './components/HelloWorld.vue'
import NavBar from '../src/components/Navbar/NavBar.vue'
import PieChart from './components/PieChart/PieCharts.vue' // 👈 import the pie chart
</script>

<template>
  <NavBar />
  <div class="p-4">
    <h1>Pie Chart Example</h1>
    <PieChart /> <!-- 👈 add the pie chart component -->
  </div>
</template>

<style scoped>
/* Optional styling */
h1 {
  text-align: center;
  margin-bottom: 1rem;
}
</style>
