<template>
  <div>
    <h2>Palette</h2>
    <div class="palette">
      <Color
        v-for="(color, index) in colors"
        v-bind:color="color"
        v-bind:index="index"
        v-bind:key="index"
      />
    </div>
  </div>
</template>

<script>
import Color from './Color'

export default {
  name: 'Palette',
  components: {
    Color
  },
  props: ['colors']
}
</script>

<style scoped>
.palette {
  display: flex;
  flex-direction: row;
  justify-items: space-between;
  width: 100%;
  margin-bottom: 64px;
  padding: 0.5vw;
}
</style>
