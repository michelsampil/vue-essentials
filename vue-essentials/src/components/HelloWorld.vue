<script>
export default {
  data() {
    return {
      msg: 'Hello World! 🥔🚀'
    }
  }
}
</script>

<template>
  <h1>{{ msg }}</h1>
  <input v-model="msg">
  <a v-bind:href="msg"> Time to Fly! </a>
</template>

<style scoped>
div {
  color: #02AAB0;
  background-color: #35495e;
  padding: 2vw;
}

input {
  font-size: medium;
  padding: 15px 45px;
}
</style>

