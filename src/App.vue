<template>
  <div style="position: absolute; top:0; width: 100% !important;">
    <Nav @setActivePopup="setActivePopup" :active-popup="activePopup"/>
  </div>
   <div>
     <div>
       <home-tab/>
     </div>
     <div v-if="activePopup" id="popup">
       <plc-tab />
     </div>
   </div>
</template>

<script>
import Nav from "@/components/navbar/Nav";
import HomeTab from "@/components/tabs/homeTab";
import PlcTab from "@/components/tabs/plcTab";

export default {
  name: 'App',
  components: {
    PlcTab,
    HomeTab,
    Nav,
  },
  data() {
    return {
      activePopup: false
    }
  },
  methods: {
    setActivePopup() {
      this.activePopup = !this.activePopup
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
#popup {
  display: table;
  margin-right: auto;
  margin-left: auto;
  margin-top: 15%;
}
</style>
