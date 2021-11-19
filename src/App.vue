<template>
  <div id="app" class="col">
    <router-view/>
  </div>
</template>
<script>
export default {
  
}
</script>
<style>
body{
  background: rgb(31,33,46);
  background: linear-gradient(180deg, rgba(31,33,46,1) 0%, rgba(31,33,46,1) 28%, rgba(30,32,42,1) 28%);
}
#app {
  font-family: ('https://fonts.google.com/specimen/Inter');
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: hsl(228, 34%, 66%);
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
