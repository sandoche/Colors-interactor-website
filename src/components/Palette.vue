<template>
  <div class="palette">
    <Color
      v-for="(color, index) in colors"
      v-bind:color="color"
      v-bind:key="index"
    />
  </div>
</template>

<script>
import Color from './Color'

export default {
  components: {
    Color
  },
  name: 'Palette',
  props: ['colors']
}
</script>

<style scoped>
.palette {
  display: flex;
  flex-direction: row;
  justify-items: space-between;
  width: 100%;
}
</style>
