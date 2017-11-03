<template>
  <div class="color-container" v-bind:style="{backgroundColor: color}">
    <div class="color" v-on:click="toggle">
      {{ color }}
    </div>
    <Chrome v-if="show" v-model="colorPicker" @input="updateValue"/>
  </div>
</template>

<script>
import { Chrome } from 'vue-color'

export default {
  name: 'Color',
  components: {
    Chrome
  },
  props: ['color', 'index'],
  data: function () {
    return {
      show: false,
      colorPicker: {
        hex: this.color
      }
    }
  },
  methods: {
    updateValue: function (value) {
      // Todo: change this using emit
      console.log(value.hsl.l)
      this.$parent.$parent.updateColor(value.hex, this.index)
    },
    toggle: function () {
      this.show = !this.show
    }
  }
}
</script>

<style>
.color-container {
  display:flex;
  flex: 1;
  flex-direction: column;
  height: 350px;
  text-align: center;
  justify-content: center;
  align-items: center;
  padding-bottom: 10px;
}

.color {
  display:flex;
  flex: 1;
  text-align: center;
  padding: 10px;
  align-items: flex-start;
  justify-content: center;
  min-height: 50px;
  font-size: 24px;
  cursor: pointer;
  width: 100%;
}
</style>
