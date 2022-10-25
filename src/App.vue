<template>
  <div style="position: absolute; z-index: 10; display: flex; justify-content: center;">
    <Nav />
  </div>
  <div style="position: absolute; margin-top: 500px;">
    <AFrame />
  </div>
</template>

<script>
import AFrame from "@/components/Aframe";
import Nav from "@/components/navbar/Nav";

export default {
  name: 'App',
  components: {
    Nav,
    AFrame,
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
