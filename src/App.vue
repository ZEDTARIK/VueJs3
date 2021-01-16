<template>
  <img alt="Vue logo" src="./assets/logo.png">

    {{ message }}    

  <input type="text" ref="book">
  <button @click="handlClick()">Click</button>
</template>

<script>

export default {
  name: 'App',  
  data() {
    return {
      message : 'Formation VueJs 3'
    }
  },
  methods: {
    handlClick() {
      this.$refs.book.classList.add('active');
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
