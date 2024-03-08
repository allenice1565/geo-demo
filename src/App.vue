<script setup>
import * as echarts from 'echarts'
import { ref, onMounted } from 'vue'
import geoJSON from '@assets/geo-json/SC.json'

const chartEl = ref(null)
const chartInstance = ref(null)
onMounted(() => {
    chartInstance.value = echarts.init(chartEl.value)
    echarts.registerMap('SC', { geoJSON })
    chartInstance.value.setOption({
        geo: {
            show: true,
            map: 'SC',
            nameProperty: 'name',
            selectedMode: 'single',
            // label: {
            //     // show: true,
            //     formatter(data) {
            //         return data.name
            //     },
            // },
            itemStyle: {
                areaColor: '#fff',
            },
            emphasis: {
                itemStyle: {
                    areaColor: 'skyblue',
                },
            },
            select: {
                itemStyle: {
                    areaColor: 'skyblue',
                },
            },
            tooltip: {
                formatter(data) {
                    return data.name
                },
                backgroundColor: 'pink',
            },
        },
        tooltip: {
            show: true,
        },
        // data: [
        //     {
        //         name: '成都市',
        //         value: 1,
        //     },
        //     {
        //         name: '自贡市',
        //         value: 1,
        //     },
        //     {
        //         name: '攀枝花市',
        //     },
        //     {
        //         name: '泸州市',
        //     },
        //     {
        //         name: '德阳市',
        //     },
        //     {
        //         name: '绵阳市',
        //     },
        //     {
        //         name: '广元市',
        //     },
        //     {
        //         name: '遂宁市',
        //     },
        //     {
        //         name: '内江市',
        //     },
        //     {
        //         name: '乐山市',
        //     },
        //     {
        //         name: '南充市',
        //     },
        //     {
        //         name: '眉山市',
        //     },
        //     {
        //         name: '宜宾市',
        //     },
        //     {
        //         name: '广安市',
        //     },
        //     {
        //         name: '达州市',
        //     },
        //     {
        //         name: '雅安市',
        //     },
        //     {
        //         name: '巴中市',
        //     },
        //     {
        //         name: '资阳市',
        //     },
        //     {
        //         name: '阿坝藏族羌族自治州',
        //     },
        //     {
        //         name: '甘孜藏族自治州',
        //     },
        //     {
        //         name: '凉山彝族自治州',
        //     },
        // ],
    })
})
</script>

<template>
    <div class="app-container">
        <div class="geo-container" ref="chartEl"></div>
    </div>
</template>

<style scoped>
.app-container {
    width: 100%;
}
.geo-container {
    width: 100%;
    height: 600px;
}
</style>
@/assets/geo-json/SC
