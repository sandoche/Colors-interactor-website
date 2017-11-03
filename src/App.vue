<template>
  <div id="app">
    <Palette :colors='colors'/>
    <button class='button' v-on:click='updateAllColors'>Get new colors</button>
    <ColorsSquare :colors='colors'
      v-for="(num, index) in mixes"
      v-bind:index="num"
      v-bind:key="index"
    />
  </div>
</template>

<script>
import Palette from './components/Palette'
import ColorsSquare from './components/ColorsSquare'
import randomColor from 'randomcolor'

export default {
  name: 'app',
  components: {
    Palette,
    ColorsSquare
  },
  data: function () {
    return {
      // Todo: randomize the choice
      colors: randomColor({count: 5}),
      mixes: [0, 1, 2, 3, 4]
    }
  },
  methods: {
    updateColor: function (color, index) {
      const newColors = Object.assign({}, this.colors)
      newColors[index] = color
      this.colors = newColors
    },
    updateAllColors: function () {
      const newColors = randomColor({count: 5})
      this.colors = newColors
    }
  }
}
</script>

<style>
#app {
}

.button {
  display: inline-block;
  border: 3px solid #fff;
  padding: 12px 22px;
  font-weight: 300;
  cursor: pointer;
  background-color: #252525;
  color: #fff;
  margin-left: 8px;
  margin-bottom: 64px;
}

.button:hover {
  color: #252525;
  background-color: #fff;
}
</style>
