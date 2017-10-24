<template>
  <div class="palette">
    <Color
      v-for="(color, index) in colors"
      v-bind:color="color"
      v-bind:index="index"
      v-bind:update-color="updateColor"
      v-bind:key="index"
    />
  </div>
</template>

<script>
import Color from './Color'

export default {
  name: 'Palette',
  components: {
    Color
  },
  props: ['colors', 'updateColor']
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
