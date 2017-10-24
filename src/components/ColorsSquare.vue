<template>
  <div class="colors-square" v-bind:style="{ backgroundColor: colors[0] }">
    <h1>Color square</h1>
  </div>
</template>

<script>
export default {
  name: 'ColorsSquare',
  props: ['colors']
}
</script>

<style>
.colors-square {
}
</style>
