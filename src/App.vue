<script setup>
import NavBar from "../src/components/Navbar/NavBar.vue";
import PieChart from "./components/PieChart/PieCharts.vue"; // 👈 import the pie chart
import MovieTable from "./components/MovieTable.vue"; // 👈 import the pie chart
</script>

<template>
  <NavBar />
  
    <PieChart />
 
  <MovieTable />
 
</template>

<style scoped>
/* Optional styling */
h1 {
  text-align: center;
  margin-bottom: 1rem;
}
body {
  background-color: #f9f9f9;
}

</style>
