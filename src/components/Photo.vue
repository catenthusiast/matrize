<template>
  <div class="photo">
    <svg width="0" height="0">
      <filter id="myFilter">
        <feColorMatrix type="matrix" :values='values'/>
      </filter>
    </svg>
    <img :src="src" alt="Photo" style="filter: url(#myFilter)">
  </div>
</template>

<script>
  export default {
    name: 'photo',
    props: [ 'values' ],
    data () {
      return {
        src: '/static/mountains.jpg'
      }
    }
  }
</script>

<style>
.photo {
  grid-column: 1 / 2;
  grid-row: 1 / 2;
}

.photo img {
  width: 100%;
  height: 100%;
}
</style>
