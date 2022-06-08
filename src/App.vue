<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

  margin-top: 60px;
}
body.dark-mode {
  background-color: #242424;
  color: #b7b7b7;
}
body.dark-mode .flex h1 {
  color: #fff;
}
body.dark-mode .mode-toggle {
  background-color: #333333;
}
body.dark-mode .mode-toggle .toggle {
  transform: translateX(19px);
}
body.dark-mode .mode-toggle .toggle #dark-mode:before {
  border-radius: 50%;
  width: 150%;
  height: 85%;
  left: 40%;
  transform: translate(-10%, -40%), rotate(-35deg);
}
</style>
