<template>
  <div id="app">
    <photo :values="matrixString"></photo>
    <svg-output :outputDisplay="matrixBox"></svg-output>
    <div class="controllers">
      <channel-controller v-for="channel in channels" :chan="channel"></channel-controller>
    </div>
  </div>
</template>

<script>
import Photo from './components/Photo'
import SvgOutput from './components/SvgOutput'
import ChannelController from './components/ChannelController'
import R from 'ramda'

export default {
  name: 'app',
  data: function () {
    return {
      channels: [
        {name: 'red', values: [ 1, 0, 0, 0, 0 ]},
        {name: 'green', values: [ 0, 1, 0, 0, 0 ]},
        {name: 'blue', values: [ 0, 0, 1, 0, 0 ]},
        {name: 'alpha', values: [ 0, 0, 0, 1, 0 ]}
      ]
    }
  },
  computed: {
    matrixValues: function () {
      return R.flatten(R.pluck('values', this.channels))
    },
    matrixString: function () {
      return R.join(' ', this.matrixValues)
    },
    matrixBox: function () {
      return this.matrixString.substring(0, 9) + '\n' + this.matrixString.substring(10, 19) + '\n' + this.matrixString.substring(20, 29) + '\n' + this.matrixString.substring(30, 39)
    }
  },
  components: {
    Photo,
    SvgOutput,
    ChannelController
  }
}
</script>

<style>
#app {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto auto;
  justify-items: start;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.controllers{
  grid-column: 1 / 3;
  grid-row: 2 / 3;
}
</style>
