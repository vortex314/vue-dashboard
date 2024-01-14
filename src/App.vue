<script setup>
import Gauge from './components/Gauge.vue'
import Row from './components/Row.vue'
import Dashboard from './components/Dashboard.vue'
import Col from './components/Col.vue'
import Button from './components/Button.vue'
import { ref, onMounted, reactive } from 'vue'

const theme = { 
  background_color: 0x000000,
  border_color: 0x2ddeeb,
  text_color: 0x2222EE,
  button_color: 0x2ddeeb,

}
</script>

<template>
  <Dashboard :h=768 :w=1024>
    <Row :h=150>
      <Gauge :w=100 label="Bytes" src="src/esp32/sys/heap" :minValue=0.0 :maxValue=50000.0 />
      <Gauge :w=200 label="°C" src="src/esp32/sys/temp" :minValue=0.0 :maxValue=1000.0 />
      <Gauge :w=300 label="Gauge3"/>
      <Gauge :w=400 label ="Gauge4"/>
    </Row>
    <Col :w=100>
      <Button :w=100 :h=100 label="Please reset."/>
    </Col>
  </Dashboard>
</template>

<style scoped>
</style>
