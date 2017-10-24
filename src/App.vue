<template>
  <div id="app">
    <Palette :colors='colors'/>
    <ColorsSquare :colors='colors'/>
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
  }
}
</script>

<style>
#app {
}
</style>
