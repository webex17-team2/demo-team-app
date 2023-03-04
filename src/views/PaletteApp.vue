<template>
  <h1>Vue パレット</h1>
  <div class="app">
    <div
      class="palette"
      v-on:mousemove="changeColor"
      v-on:click="pickColor"
      v-bind:style="paletteStyle"
    ></div>
    <p>rgba({{ red }}, {{ green }},200,0.5)</p>
    <div class="colors-container">
      <div
        class="mini-palette"
        v-for="(color, index) in colors"
        v-bind:key="index"
        v-bind:style="{
          backgroundColor: `rgba(${color.red},${color.green},200,0.5)`,
        }"
        v-on:click="showColor(color)"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      red: 0,
      green: 0,
      colors: [],
    }
  },
  methods: {
    changeColor(event) {
      this.red = event.offsetX
      this.green = event.offsetY
      console.log(this.red)
    },
    pickColor() {
      const newColor = {
        red: this.red,
        green: this.green,
      }
      this.colors.push(newColor)
      console.log(newColor)
      console.log(this.colors)
    },
    showColor(color) {
      this.red = color.red
      this.green = color.green
    },
  },

  computed: {
    paletteStyle() {
      return {
        backgroundColor: `rgba(${this.red},${this.green}, 200, 0.5)`,
      }
    },
  },
}
</script>
<style>
.app {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: center;
}
.palette {
  width: 300px;
  height: 300px;
}
.mini-palette {
  min-width: 60px;
  height: 60px;
}
.colors-container {
  display: flex;
  flex-wrap: wrap;
  width: 300px;
  padding-top: 8px;
}
</style>
