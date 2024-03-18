<script setup>
import * as echarts from 'echarts'
import { ref, onMounted, onUnmounted } from 'vue'
// import geoJSON from '@assets/geo-json/data.json'
import geoJSON from '@assets/geo-json/SC.json'

const chartEl = ref(null)
const chartInstance = ref(null)
const dataset = ref([
    {
        name: '成都市',
        value: 99,
    },
    {
        name: '绵阳市',
        value: 103,
    },
])
onMounted(() => {
    chartInstance.value = echarts.init(chartEl.value)
    echarts.registerMap('SC', { geoJSON })
    // chartInstance.value.setOption({
    //     // geo: {
    //     //     show: true,
    //     //     map: 'HC',
    //     //     nameProperty: 'name',
    //     //     selectedMode: 'single',
    //     //     label: {
    //     //         show: true,
    //     //         formatter(data) {
    //     //             return data.name
    //     //         },
    //     //     },
    //     //     itemStyle: {
    //     //         areaColor: '#fff',
    //     //     },
    //     //     emphasis: {
    //     //         itemStyle: {
    //     //             areaColor: 'skyblue',
    //     //         },
    //     //     },
    //     //     select: {
    //     //         itemStyle: {
    //     //             areaColor: 'skyblue',
    //     //         },
    //     //     },
    //     //     tooltip: {
    //     //         formatter(data) {
    //     //             return data.name
    //     //         },
    //     //         backgroundColor: 'pink',
    //     //     },
    //     // },
    //     label: {
    //         show: true,
    //         formatter(data) {
    //             return data.name
    //         },
    //     },
    //     tooltip: {
    //         show: true,
    //         position: 'inside',
    //         formatter(data) {
    //             return data.name
    //         },
    //         backgroundColor: 'pink',
    //     },
    //     series: [
    //         {
    //             type: 'map',
    //             map: 'SC',
    //             coordinateSystem: 'geo',
    //             symbol: 'circle',
    //             data: [
    //                 {
    //                     name: '成都市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '自贡市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '攀枝花市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '泸州市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '德阳市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '绵阳市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '广元市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '遂宁市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '内江市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '乐山市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '南充市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '眉山市',
    //                 },
    //                 {
    //                     name: '宜宾市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '广安市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '达州市',
    //                 },
    //                 {
    //                     name: '雅安市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '巴中市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '资阳市',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '阿坝藏族羌族自治州',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '甘孜藏族自治州',
    //                     value: 1,
    //                 },
    //                 {
    //                     name: '凉山彝族自治州',
    //                     value: 1,
    //                 },
    //             ],
    //         },
    //     ],
    // })
    // chartInstance.value.setOption(
    //     {
    //         tooltip: {
    //             show: true,
    //             formatter(v) {
    //                 const div = document.createElement('div')
    //                 div.style.borderRadius = '10px'
    //                 div.innerHTML = `
    //               <div style="width:218px;height:98px;padding:17px 20px 28px;">
    //                   <div style="font-weight: 500;font-size: 20px;color: #FFFFFF;line-height: 20px;">tooltip</div>
    //                   <div style="display:flex;align-items:flex-end;height:18px;margin-top:12px;">
    //                       <div style="font-weight: bold;font-size: 24px;color: #FFFFFF;line-height: 18px;height:18px;">123</div>
    //                       <div style="margin-left:6px;font-weight: bold;font-size: 14px;color: #FFFFFF;line-height: 14px;">占比231</div>
    //                   </div>
    //               </div>
    //               `
    //                 return div
    //             },
    //             backgroundColor: '#4373F1',
    //             extraCssText: {
    //                 borderRadius: '10px',
    //             },
    //             position(point, params, dom, rect) {
    //                 return [
    //                     point[0] - rect.width / 2 + 10,
    //                     point[1] - rect.height / 2 - 30,
    //                 ]
    //             },
    //         },
    //         // geo: {
    //         //     label: {
    //         //         show: true,
    //         //         formatter(v) {
    //         //             return v.name
    //         //         },
    //         //         position: ['50%', '80%'],
    //         //     },
    //         // },
    //         series: [
    //             {
    //                 type: 'map',
    //                 map: 'HC',
    //                 coordinateSystem: 'geo',
    //                 symbol: 'circle',
    //                 itemStyle: {
    //                     areaColor: '#fff',
    //                     shadowBlur: '#96B1F7',
    //                     borderWidth: 1,
    //                     borderColor: '#96B1F7',
    //                 },
    //                 emphasis: {
    //                     itemStyle: {
    //                         areaColor: '#92ACF0',
    //                     },
    //                 },
    //                 data: [
    //                     {
    //                         name: '团泽镇',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '芝麻镇',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '攀枝花市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '泸州市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '德阳市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '绵阳市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '广元市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '遂宁市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '内江市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '乐山市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '南充市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '眉山市',
    //                     },
    //                     {
    //                         name: '宜宾市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '广安市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '达州市',
    //                     },
    //                     {
    //                         name: '雅安市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '巴中市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '资阳市',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '阿坝藏族羌族自治州',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '甘孜藏族自治州',
    //                         value: 1,
    //                     },
    //                     {
    //                         name: '凉山彝族自治州',
    //                         value: 1,
    //                     },
    //                 ],
    //             },
    //         ],
    //     },
    //     { notMerge: true }
    // )
    // chartInstance.value.dispatchAction({
    //     type: 'showTip',
    //     seriesIndex: 0,
    //     dataIndex: 0,
    // })
    chartInstance.value.setOption({
        dataset: {
            source: dataset.value,
        },
        geo: {
            map: 'SC',
        },
        tooltip: {
            position(point, params, dom, rect) {
                console.log('xxx', {
                    ...point,
                    name: params.name,
                    width: rect.width,
                    height: rect.height,
                })
                return [point[0] - rect.width / 2, point[1] - 60]
            },
            formatter(item) {
                return item.name
            },
        },
        series: [
            {
                type: 'map',
                map: 'SC',
            },
        ],
    })
    chartInstance.value.dispatchAction({
        type: 'showTip',
        seriesIndex: 0,
        dataIndex: 0,
    })
})
onUnmounted(() => {
    chartInstance.value.dispose()
    chartInstance.value = null
})
</script>

<template>
    <div class="app-container">
        <div class="geo-container" ref="chartEl"></div>
    </div>
</template>

<style scoped>
.app-container {
    width: 500px;
}
.geo-container {
    width: 100%;
    height: 600px;
}
</style>
