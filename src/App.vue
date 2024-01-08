<script setup>
import Gauge from './components/Gauge.vue'
import Row from './components/Row.vue'
import Dashboard from './components/Dashboard.vue'
import Col from './components/Col.vue'
import Button from './components/Button.vue'
import { ref, onMounted, reactive } from 'vue'

const title = reactive({ name: "My Title" })

</script>

<template>
  <Dashboard :h=768 :w=1024>
    <Row :h=200>
      <Gauge :w=100 src="src/esp32/sys/heap" :min=0.0 :max=50000.0 />
      <Gauge :w=200 />
      <Gauge :w=300 />
      <Gauge :w=400 />
    </Row>
    <Col :w=100>
      <Button :w=100 :h=100 label="Please reset."/>
    </Col>
  </Dashboard>
</template>

<style scoped>
</style>
