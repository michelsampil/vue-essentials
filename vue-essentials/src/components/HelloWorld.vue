<script>
export default {
  data() {
    return {
      msg: 'Hello World! 🚀'
    }
  }
}
</script>

<template>
  <h1>{{ msg }}</h1>
  <a v-bind:href="msg">Time to Fly!</a>
  <input v-model="msg">
</template>

<style scoped>
  div{
    color: #02AAB0;
    background-color: #35495e;
    padding: 2vw;
  }
</style>

