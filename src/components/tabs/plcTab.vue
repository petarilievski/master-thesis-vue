<template>
  <div class="container">
    <div style="width:35%">
        <left-component/>
    </div>
    <div style="width:65%;">
      <right-component />
    </div>
  </div>
</template>

<script>
import LeftComponent from "@/components/subtabs/plc/leftComponent";
import RightComponent from "@/components/subtabs/plc/rightComponent";
export default {
  name: "plcTab",
  components: {
    RightComponent,
    LeftComponent}
}
</script>

<style scoped>
.container {
  display: flex;
  /*justify-content: space-between;*/
}
</style>