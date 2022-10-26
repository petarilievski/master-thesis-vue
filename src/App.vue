<template>
    <Nav @setActiveTab="setActiveTab" :active-tab="activeTab"/>
   <div style="padding: 2%">
     <div v-if="activeTab === 0">
       <home-tab/>
     </div>
     <div v-else>
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
