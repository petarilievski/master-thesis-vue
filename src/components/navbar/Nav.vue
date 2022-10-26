<template>
  <div class="container">
    <div class="subcontainer">
      <img src="../../../public/assets/FEIT-logo.png" alt="FEEIT" height="50" width="50"/>
      <div style="color: black; font-weight: bolder; align-items: center; display: flex">Virtual&nbsp;Laboratory</div>
    </div>

    <div class="subcontainer">
      <div style="color:dodgerblue;" class="tab">Home</div>
      <div :style="this.activePopup ? 'color:dodgerblue;' : ''" @click="setActivePopup" class="tab">PLC</div>
    </div>

  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Nav',
  props: ['activePopup'],
  methods: {
    setActivePopup() {
      this.$emit('setActivePopup')
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