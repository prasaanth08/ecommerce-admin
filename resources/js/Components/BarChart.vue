<script setup>
import { onMounted, ref } from 'vue'
import Chart from 'chart.js/auto'

const chartRef = ref(null)

onMounted(() => {
    new Chart(chartRef.value, {
        type: 'bar',
        data: {
            labels: ['Jan', 'Feb', 'Mar', 'Apr'],
            datasets: [{
                label: 'Orders',
                data: [10, 20, 15, 25],
                borderWidth: 1
            }]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false
        }
    })
})
</script>

<template>
    <div class="h-64">
        <canvas ref="chartRef"></canvas>
    </div>
</template>