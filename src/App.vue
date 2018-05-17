<template>
  <div id="app">
    <div class="logo">
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  width: 100%;
  padding: 0;
  width: 100%;
}

img {
  width: 100%;
}
.logo{
  width: 100px;
}

h1 {
  margin: 0;
}
</style>
