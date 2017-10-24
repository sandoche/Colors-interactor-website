<template>
  <div id="app">
    <ColorsSquare :colors='colors'/>
  </div>
</template>

<script>
import ColorsSquare from './components/ColorsSquare'

export default {
  name: 'app',
  components: {
    ColorsSquare
  },
  data: function () {
    return {
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
