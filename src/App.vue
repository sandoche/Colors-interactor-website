<template>
  <div id="app">
    <Palette :colors='colors'/>
    <ColorsSquare :colors='colors' :update-color='updateColor'/>
    {{ colors }}
  </div>
</template>

<script>
import Palette from './components/Palette'
import ColorsSquare from './components/ColorsSquare'

export default {
  name: 'app',
  components: {
    Palette,
    ColorsSquare
  },
  data: function () {
    return {
      // Todo: randomize the choice
      colors: [
        '#e9a138',
        '#771cc6',
        '#7c300a',
        '#47b329',
        '#f2078b'
      ]
    }
  },
  methods: {
    updateColor: function (color, index) {
      const newColors = Object.assign({}, this.colors)
      newColors[index] = color
      this.colors = newColors
    }
  }
}
</script>

<style>
#app {
}
</style>
