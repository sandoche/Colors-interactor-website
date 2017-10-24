<template>
  <div class="color-container">
    <div class="color" v-bind:style="{backgroundColor: color}" v-on:click="toggle">
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
  props: ['color', 'index', 'updateColor'],
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
}

.color {
  display:flex;
  flex: 1;
  text-align: center;
  padding: 10px;
}
</style>
