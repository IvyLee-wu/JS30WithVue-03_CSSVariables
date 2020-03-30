<template>
  <div id="app">
    <h2>
      Update CSS Variables with
      <span :style="spanStyle">JS</span>
    </h2>

    <div class="controls">
      <label for="spacing">Spacing:</label>
      <input type="range" id="spacing" v-model="spacing" min="10" max="200" />

      <label for="blur">Blur:</label>
      <input type="range" id="blur" v-model="blur" min="0" max="25" />

      <label for="base">Base Color</label>
      <input type="color" id="base" v-model="base" />
    </div>

    <img src="https://source.unsplash.com/7bwQXzbF6KE/800x500" :style="imgStyle"/>
  </div>
</template>

<script>

export default {
  name: 'App',
  data () {
    return {
      spacing: 10,
      blur: 10,
      base: '#ffc600'
    }
  },
  computed: {
    spanStyle () {
      return {
        color: this.base
      }
    },
    imgStyle () {
      return {
        padding: `${this.spacing}px`,
        'background-color': this.base,
        filter: `blur(${this.blur}px)`
      }
    }
  }
}
</script>

<style>
body {
  text-align: center;
  background: #193549;
  color: white;
  font-family: 'helvetica neue', sans-serif;
  font-weight: 90;
  font-size: 30px;
}

.controls {
  margin-bottom: 50px;
}

input {
  width: 100px;
}
</style>
