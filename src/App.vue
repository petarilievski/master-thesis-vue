<template>
    <Nav @setActiveTab="setActiveTab" :active-tab="activeTab"/>

<!--  <div style="position: absolute; margin-top: 500px;">-->
<!--    <AFrame />-->
<!--  </div>-->
</template>

<script>
// import AFrame from "@/components/Aframe";
import Nav from "@/components/navbar/Nav";

export default {
  name: 'App',
  components: {
    Nav,
    // AFrame,
  },
  data() {
    return {
      activeTab: 0
    }
  },
  methods: {
    setActiveTab(tab) {
      this.activeTab = tab
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
