<script setup>
import VueApexCharts from "vue3-apexcharts"

const series = [
    {
        name: "Orders",
        data: [10, 25, 18, 30, 22, 40]
    }
]
const chartOptions = {
    chart: {
        type: 'bar',
        toolbar: { show: false }
    },
    colors: ['#008FFB', '#00E396', '#FEB019', '#FF4560'],
    plotOptions: {
        bar: {
            borderRadius: 8,
            columnWidth: '50%'
        }
    },
    dataLabels: {
        enabled: false
    },
    xaxis: {
        categories: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun']
    },
    grid: {
        borderColor: '#e7e7e7'
    }
}
</script>
<template>
    <div class="w-full">
        <VueApexCharts 
            type="bar" 
            height="300" 
            :options="chartOptions" 
            :series="series" 
        />
    </div>
</template>