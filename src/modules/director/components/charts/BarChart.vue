<template>
  <Bar :data="props.data" :options="props.options" />
</template>

<script setup lang="ts">
import { Bar } from 'vue-chartjs'
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale,
  type ChartData,
} from 'chart.js'
import { withDefaults } from 'vue'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

type BarChartData = ChartData<'bar'>

const props = withDefaults(defineProps<{
  data?: BarChartData
  options?: Record<string, unknown>
}>(), {
  data: () => ({ labels: [], datasets: [] }),
  options: () => ({}),
})
</script>
