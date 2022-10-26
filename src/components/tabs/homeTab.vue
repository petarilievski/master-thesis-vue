<template>
    <div style="height: 100px !important; width: 100px !important;">
      <AFrame />
    </div>
  <div style="position: absolute; bottom:0; width: 100% !important;">
      <ControlsComponent />
    </div>
</template>

<script>
import AFrame from "@/components/Aframe";
import ControlsComponent from "@/components/subtabs/controlsComponent";
export default {
  name: "homeTab",
  components: {ControlsComponent, AFrame}
}
</script>

<style scoped>

</style>