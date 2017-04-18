<template>
  <div class="svg-output">
    <pre>{{ outputDisplay }}</pre>
  </div>
</template>

<script>
export default {
  name: 'svg-output',
  props: [ 'outputDisplay' ]
}
</script>

<style>
.svg-output {
  grid-column: 2 / 3;
  grid-row: 1 / 2;
  font-size: 36px;
}
</style>
