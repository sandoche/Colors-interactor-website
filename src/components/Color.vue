<template>
  <div class="color" v-bind:style="{backgroundColor: color}">
    {{ color }}
  </div>
</template>

<script>
export default {
  name: 'Color',
  props: ['color']
}
</script>

<style>
.color {
  display:flex;
  flex: 1;
  text-align: center;
  padding: 10px;
}
</style>
