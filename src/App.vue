<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div class="row ">
      <div class="col-6">
        <img src="./assets/like.png" width="15%" height="50%" alt />
        <button v-on:click="counter1 += 1" class="btn btn-primary">{{label1="like"}}</button>
        <h1>{{ counter1 }}</h1>
      </div>

      <div class="col-6">
        <img src="./assets/dislike.png" width="15%" height="50%" alt />
        <button v-on:click="counter2 -= 10" class="btn btn-primary">{{label2="Dislike"}}</button>
        <h1>{{ counter2 }}</h1>
      </div>

      <div class="col-6">
        <img src="./assets/love.png" width="15%" height="50%" alt />
        <button v-on:click="counter3 += 5" class="btn btn-primary">{{label3="Love"}}</button>
        <h1>{{ counter3 }}</h1>
      </div>

      <div class="col-6">
        <h1>Total: {{counter1+counter2+counter3}}</h1>
        <button @click="reset" class="btn btn-primary">Click to reset</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  props: {
    label1: String,
    label2: String,
    label3: String,
  },
  data: function () {
    return {
      counter1: 0,
      counter2: 0,
      counter3: 0,
      reset1: 0,
      classObject: {
        active: true,
        "text-danger": false,
        weight: 20,
      },
    };
  },
  methods: {
    reset() {
      Object.assign(this.$data, this.$options.data());
    },
  },
};
</script>

<style>
#app {
  background-color: bisque;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
