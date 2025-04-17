<script setup>
import NavBar from "../src/components/Navbar/NavBar.vue";
import PieChart from "./components/PieChart/PieCharts.vue"; 
import MovieTable from "./components/MovieTable.vue"; 
import TrendingMovie from "./components/TrendingMovie.vue";
</script>

<template>
  <NavBar />
  
    <PieChart />
 
  <MovieTable />
 <TrendingMovie />
</template>

<style scoped>

h1 {
  text-align: center;
  margin-bottom: 1rem;
}
body {
  background-color: #f9f9f9;
}

</style>
