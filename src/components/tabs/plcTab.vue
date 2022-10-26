<template>
  <div class="container">
    <left-component/>
    <right-component />
  </div>
</template>

<script>
import LeftComponent from "@/components/subtabs/plc/leftComponent";
import RightComponent from "@/components/subtabs/plc/rightComponent";
export default {
  name: "plcTab",
  components: {RightComponent, LeftComponent}
}
</script>

<style scoped>
.container {
  display: flex;
  justify-content: space-between;
}
</style>