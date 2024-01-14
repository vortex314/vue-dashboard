<script setup>
import { ref, onMounted, reactive } from 'vue'
import { RadialGauge, LinearGauge } from 'canvas-gauges'

const props = defineProps({
    h: {
        type: Number,
        default: 200
    }, w: {
        type: Number,
        default: 200
    }, minWidth: {
        type: Number,
        default: 200
    }, maxWidth: {
        type: Number,
        default: 200
    }, label: {
        type: String,
        default: "Heap"
    }, minValue: {
        type: Number,
        default: 0.0
    }, maxValue: {
        type: Number,
        default: 1.0
    }, src: {
        type: String,
        default: "src/esp32/sys/heap"
    }
})

const canvas_ref = ref(null)
const maxWidth = ref("null")

onMounted(() => {
    console.log("Gauge", props.label,props)
    let element = canvas_ref.value
    console.log("Gauge", props.label,element)
    maxWidth.value = props.w + 'px'
    let square_size = Math.min(props.w, props.h)
    let delta = props.maxValue - props.minValue
    let majorTicks= [
        props.minValue,props.maxValue/4,props.maxValue/2,3*props.maxValue/4,props.maxValue
    ];
    const gauge = new RadialGauge({
        renderTo: canvas_ref.value,
        colorNumbers: 'red',
        minValue: props.minValue,
        maxValue: props.maxValue,
        width: square_size,
        height: square_size,
        units: props.label,
        value: 0.0,
        majorTicks: majorTicks,
        title:true,
    }).draw();
})
</script>
<template>
    <canvas ref="canvas_ref"></canvas>
</template>
<style scoped>
.canvas {
    border: 1px solid #2ddeeb;
    background-color: #f1f1f1;
    padding: 0px;
    margin: 0px;
    word-wrap: break-word;
    overflow: hidden;
    inline-size: min-content;
    max-width: v-bind(maxWidth);
}
</style>