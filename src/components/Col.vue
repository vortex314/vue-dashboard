<script setup>
import { ref, onMounted,reactive } from 'vue'
const props = defineProps({h: Number, w: Number})

</script>
<template>
    <div class="vertical" :width="w" >
        width : {{  w  }}
        Let's place here a very loooooooooooooooooooooooooooooooooooooooooooong text
        <slot>Fallback slot for Row</slot>
    </div>
</template>

<style scoped>
div {
    border: 4px solid #2ddeeb;
    background-color: #f1f1f1;
    padding: 10px;
    margin: 1px;
    word-wrap: break-word;
    overflow: hidden;
    inline-size:min-content;
}   
.vertical {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    height: 100%;
}
</style>
