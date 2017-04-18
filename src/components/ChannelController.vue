<template>
  <div class="channel-controller">
    <h1>{{ chan.name }}</h1>
    <input type="range" min="0" max="2" step="0.1" v-model="chan.values[0]">
    <input type="range" min="0" max="2" step="0.1" v-model="chan.values[1]">
    <input type="range" min="0" max="2" step="0.1" v-model="chan.values[2]">
    <input type="range" min="0" max="2" step="0.1" v-model="chan.values[3]">
    <input type="range" min="0" max="2" step="0.1" v-model="chan.values[4]">
  </div>
</template>

<script>
export default {
  name: 'channel-controller',
  props: [ 'chan' ]
}
</script>

<style>
</style>
