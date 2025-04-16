<template>
    <div class="chart-card">
      <h3>Today's user logins</h3>
      <Doughnut :data="chartData" :options="chartOptions" />
      <button>View full report</button>
    </div>
  </template>
  
  <script setup>
  import {
    Chart as ChartJS,
    Title,
    Tooltip,
    Legend,
    ArcElement,
    DoughnutController,
  } from 'chart.js'
  import { Doughnut } from 'vue-chartjs'
  
  ChartJS.register(Title, Tooltip, Legend, ArcElement, DoughnutController)
  
  // Simulated data and color ranges
  const chartData = {
    labels: [
      '0 - 1K',
      '1K - 10K',
      '10K - 100K',
      'Gradient A', 'Gradient B', 'Gradient C', 'Gradient D', 'Gradient E', 'Gradient F'
    ],
    datasets: [
      {
        label: 'User Logins',
        data: [500, 3000, 25000, 5000, 5000, 5000, 5000, 5000, 5000], // Fake slices to simulate gradient
        backgroundColor: [
          '#A6B3F0', // 0 - 1K
          '#7281D3', // 1K - 10K
          '#4755A8', // 10K - 100K
          '#35C3F3', '#8B9FE8', '#E681D8', '#FFA9A4', '#FED2CE', '#FED2CE' // Gradient look
        ],
        borderWidth: 0,
        hoverOffset: 8
      }
    ]
  }
  
  const chartOptions = {
    cutout: '60%',
    responsive: true,
    plugins: {
      legend: {
        position: 'bottom',
        labels: {
          filter: function(item, chart) {
            // Only show real ranges in legend, hide gradient slices
            return item.text.includes('-');
          }
        }
      }
    }
  }
  </script>
  
  <style scoped>
  .chart-card {
    background: white;
    padding: 20px;
    border-radius: 12px;
    width: 100%;
    max-width: 400px;
  }
  button {
    margin-top: 10px;
    background: #4755A8;
    color: white;
    padding: 6px 12px;
    border: none;
    border-radius: 6px;
    cursor: pointer;
  }
  button:hover {
    background: #7281D3;
  }
  </style>
  