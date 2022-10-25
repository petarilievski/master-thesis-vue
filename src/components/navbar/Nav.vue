<template>
  <div class="container">
    <div class="subcontainer">
      <img src="../../assets/FEIT-logo.png" alt="FEEIT" height="50" width="50"/>
      <div style="color: black; font-weight: bolder; align-items: center; display: flex">Virtual&nbsp;Laboratory</div>
    </div>

    <div class="subcontainer">
      <div :style="this.activeTab === 0 ? 'color:dodgerblue;' : ''" @click="setActiveTab(0)" class="tab">Home</div>
      <div :style="this.activeTab === 1 ? 'color:dodgerblue;' : ''" @click="setActiveTab(1)" class="tab">PLC</div>
    </div>

  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Nav',
  props: ['activeTab'],
  data() {
    return {
    }
  },
  methods: {
    setActiveTab(tab) {
      this.$emit('setActiveTab', tab)
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: lightgray;
  max-width: 100%;
  padding: 1% 10%;
  font-weight: bold;
}
.subcontainer {
  display: flex;
  gap: 15%;
}
.tab {
  color:black
}
.tab:hover {
  color:dodgerblue;
  cursor: pointer;
}
</style>