<template>
  <div class="color-container">
    <div class="color" v-bind:style="{backgroundColor: color}">
      {{ color }}
    </div>
    <Chrome v-model="colorPicker" @input="updateValue"/>
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
      colorPicker: {
        hex: this.color
      }
    }
  },
  methods: {
    updateValue: function (value) {
      this.$parent.$parent.updateColor(value.hex, this.index)
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
