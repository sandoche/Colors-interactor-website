<template>
  <div class="colors-square">
    <div class="colors-square__row">
      <div class="square__parent" v-bind:style="{backgroundColor: shuffledColors[1]}">
        <div class="square__child"  v-bind:style="{backgroundColor: shuffledColors[0]}">
        </div>
      </div>
      <div class="square__parent" v-bind:style="{backgroundColor: shuffledColors[2]}">
        <div class="square__child"  v-bind:style="{backgroundColor: shuffledColors[0]}">
        </div>
      </div>
    </div>
    <div class="colors-square__row">
      <div class="square__parent" v-bind:style="{backgroundColor: shuffledColors[3]}">
        <div class="square__child"  v-bind:style="{backgroundColor: shuffledColors[0]}">
        </div>
      </div>
      <div class="square__parent" v-bind:style="{backgroundColor: shuffledColors[4]}">
        <div class="square__child"  v-bind:style="{backgroundColor: shuffledColors[0]}">
        </div>
      </div>
    </div>
    {{ shuffledColors }}
  </div>
</template>

<script>
export default {
  name: 'ColorsSquare',
  props: ['colors', 'index'],
  data: function () {
    let index = this.index
    let shuffledColors = this.colors.slice()
    shuffledColors.splice(index, 1)
    shuffledColors = [this.colors[index], ...shuffledColors]
    return {
      shuffledColors
    }
  }
}
</script>

<style>
.colors-square {
  height: 50vw;
  width: 50vw;
  display: flex;
  flex-direction: column;
}

.colors-square__row {
  display: flex;
  flex-direction: row;
  height: 50%;
  width: 100%;
}

.square__parent {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  width: 100%;
}

.square__child {
  width: 20%;
  height: 20%;
}
</style>
