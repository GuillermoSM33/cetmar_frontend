<template>
  <Doughnut :data="data" :options="options" />
</template>

<script setup lang="ts">
import { Doughnut } from 'vue-chartjs'
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  ArcElement,
} from 'chart.js'
import type { ChartData, ChartOptions } from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, ArcElement)

defineProps<{
  data: ChartData<'doughnut', number[], unknown>
  options?: ChartOptions<'doughnut'>
}>()
</script>
