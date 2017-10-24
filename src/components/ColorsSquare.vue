<template>
  <div>
    <h2 v-if="index == 0">Color plates</h2>
    <div class="colors-square">
      <div class="colors-square__row">
        <div class="square__parent" v-bind:style="{backgroundColor: colors[indexes[1]]}">
          <div class="square__child"  v-bind:style="{backgroundColor: colors[indexes[0]]}">
          </div>
        </div>
        <div class="square__parent" v-bind:style="{backgroundColor: colors[indexes[2]]}">
          <div class="square__child"  v-bind:style="{backgroundColor: colors[indexes[0]]}">
          </div>
        </div>
      </div>
      <div class="colors-square__row">
        <div class="square__parent" v-bind:style="{backgroundColor: colors[indexes[3]]}">
          <div class="square__child"  v-bind:style="{backgroundColor: colors[indexes[0]]}">
          </div>
        </div>
        <div class="square__parent" v-bind:style="{backgroundColor: colors[indexes[4]]}">
          <div class="square__child"  v-bind:style="{backgroundColor: colors[indexes[0]]}">
          </div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'ColorsSquare',
  props: ['colors', 'index'],
  data: function () {
    let index = this.index
    let indexes = [0, 1, 2, 3, 4]
    indexes.splice(index, 1)
    indexes = [index, ...indexes]
    return {
      indexes
    }
  }
}
</script>

<style>
.colors-square {
  height: 39vw;
  width: 39vw;
  display: flex;
  flex-direction: column;
  margin: 0.5vw;
  float: left;
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
