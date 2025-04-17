<template>
  <div class="dashboard">
    <h1 class="overview-title">Overview</h1>
    <div class="chart-wrapper">
      <!-- Pie Chart Card -->
      <div class="chart-card">
        <h2 class="chart-title">Today's User Logins</h2>
        <div class="chart-container">
          <Doughnut :data="chartData" :options="chartOptions" />
        </div>
        <button>View full report</button>
      </div>

      <!-- Line Chart Card -->
      <div class="chart-card">
        <h2 class="chart-title">Average Watch Time (Monthly)</h2>
        <div class="chart-container">
          <Line :data="lineChartData" :options="lineChartOptions" />
        </div>
        <button>View full report</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  ArcElement,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  DoughnutController,
} from "chart.js";
import { Doughnut, Line } from "vue-chartjs";

// Register charts
ChartJS.register(
  Title,
  Tooltip,
  Legend,
  ArcElement,
  DoughnutController,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  {
    id: "centerText",
    afterDraw: (chart) => {
      const ctx = chart.ctx;
      const centerX = (chart.chartArea.left + chart.chartArea.right) / 2;
      const centerY = (chart.chartArea.top + chart.chartArea.bottom) / 2;

      ctx.save();
      ctx.font = "bold 24px Arial";
      ctx.textAlign = "center";
      ctx.textBaseline = "middle";
      ctx.fillStyle = "#333";
      ctx.fillText("159 • 159", centerX, centerY);
      ctx.restore();
    },
  }
);

// Pie chart data
const chartData = {
  labels: ["0 - 1K", "1K - 10K", "10K - 100K", "100K - 1M"],
  datasets: [
    {
      label: "User Logins",
      data: [25, 25, 25, 25],
      backgroundColor: ["#A6B3F0", "#7281D3", "#4755A8", "#1E2A6B"],
      borderWidth: 0,
      hoverOffset: 8,
    },
  ],
};

const chartOptions = {
  cutout: "70%",
  responsive: true,
  plugins: {
    legend: {
      position: "right",
      labels: {
        usePointStyle: true,
        pointStyle: "circle",
        padding: 16,
        font: {
          size: 14,
        },
      },
    },
    tooltip: { enabled: false },
    title: { display: false },
  },
};

// Line chart data
const lineChartData = {
  labels: ["Jan", "Feb", "Mar", "Apr", "May", "Jun"],
  datasets: [
    {
      label: "Avg Watch Time (hrs)",
      data: [12, 15, 9, 14, 18, 20],
      borderColor: "#4755A8",
      backgroundColor: "#A6B3F0",
      tension: 0.3,
      fill: true,
      pointBackgroundColor: "#1E2A6B",
    },
  ],
};

const lineChartOptions = {
  responsive: true,
  plugins: {
    legend: {
      display: true,
      position: "top",
    },
    tooltip: {
      callbacks: {
        label: (ctx) => `${ctx.dataset.label}: ${ctx.parsed.y} hrs`,
      },
    },
  },
  scales: {
    y: {
      beginAtZero: true,
      title: {
        display: true,
        text: "Watch Time (hrs)",
      },
    },
    x: {
      title: {
        display: true,
        text: "Months",
      },
    },
  },
};
</script>

<style scoped>
.dashboard {
  padding: 40px 16px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.overview-title {
  font-size: 28px;
  font-weight: 700;
  color: #2c3e50;
  text-transform: uppercase;
  letter-spacing: 1px;
  margin-bottom: 32px;
  text-align: center;
  margin-right: 980px;
  margin-top: 60px;
}

.chart-wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 24px;
  width: 100%;
  max-width: 1200px;
}

.chart-card {
  background: white;
  padding: 24px;
  border-radius: 12px;
  width: 100%;
  max-width: 560px;
  border: 1px solid #e0e0e0;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.chart-title {
  font-size: 1.25rem;
  margin-bottom: 16px;
  color: #2c3e50;
  font-weight: 600;
  text-align: center;
}

.chart-container {
  width: 100%;
  height: 400px;
  margin-bottom: 16px;
}

button {
  display: block;
  margin: 0 auto;
  background: #4755a8;
  color: white;
  padding: 8px 24px;
  border-radius: 6px;
  font-size: 0.875rem;
  font-weight: 500;
  transition: background 0.2s;
  border: none;
}

button:hover {
  background: #5c6bc0;
}
</style>
