
<!-- COMPOSITION API STYLE -->
<!-- <script setup>
import { ref } from 'vue'

const count = ref(0)

function increment() {
  count.value++
}
</script>

<template>
  <div>
    <button @click="increment">count is: {{ count }}</button>
  </div>
</template>

<style scoped>
   button{
      background-image: linear-gradient(to right, #02AAB0 0%, #00CDAC 51%, #02AAB0 100%);
      margin: 10px;
      padding: 15px 45px;
      text-align: center;
      text-transform: uppercase;
      transition: 0.5s;
      background-size: 200% auto;
      color: white;            
      box-shadow: 0 0 20px #eee;
      border-radius: 10px;
    }

    button:hover {
      background-position: right center; 
      color: #fff;
      text-decoration: none;
    }

    div {
      display: flex;
      justify-content: center;
      background: #1e1e1e;
    }
</style> -->
<!-- END COMPOSITION API STYLE -->

<!-- OPTION API STYLE -->
<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    increment() {
      this.count++
    }
  }
}
</script>
<template>
  <div>
    <button @click="increment">count is: {{ count }}</button>
  </div>
</template>

<style>
   button{
      background-image: linear-gradient(to right, #02AAB0 0%, #00CDAC 51%, #02AAB0 100%);
      margin: 10px;
      padding: 15px 45px;
      text-align: center;
      text-transform: uppercase;
      transition: 0.5s;
      background-size: 200% auto;
      color: white;            
      box-shadow: 0 0 20px #eee;
      border-radius: 10px;
    }

    button:hover {
      background-position: right center; 
      color: #fff;
      text-decoration: none;
    }

    div {
      display: flex;
      justify-content: center;
      background: #1e1e1e;
    }
  
  body{
          background: #1e1e1e;
  }
</style>
<!-- END OPTION API STYLE -->