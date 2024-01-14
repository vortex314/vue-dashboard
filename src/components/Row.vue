<script setup>
import { ref, onMounted, reactive } from 'vue'
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
    }
})
const maxHight = ref(0)
const element = ref(null)

onMounted(() => {
    maxHight.value = props.h + 'px'
    console.log("Row - element", element.value.children)
    let children = element.value.children
    for (var i = 0; i < children.length; i++) {
        children[i].h = props.h + 'px'
        children[i].maxHeight = props.h + 'px'
        children[i].setAttribute("height2", props.h + "")
        children[i].setAttribute("max_height", props.h + "")

        console.log("Row - child", i, children[i])   
    }
})

</script>
<template>
    <div ref="element" :height="h" class="flex">
        <slot>Fallback slot for Row</slot>
    </div>
</template>

<style scoped>
div {
    border: 1px solid #2ddeeb;
    background-color: #f1f1f1;
    padding: 0px;
    margin: 0px;
    word-wrap: break-word;
    overflow: hidden;
    inline-size: min-content;
    width: 100%;
    max-height: v-bind(maxHight);
}

.flex {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: flex-start;
    align-items: stretch;
    align-content: stretch;
}</style>
