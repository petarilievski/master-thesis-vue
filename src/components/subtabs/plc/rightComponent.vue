<template>
  <div class="stack">
    <img src="../../../../public/assets/plc.jpg" alt="FEEIT"/>
    <div class="dot pow"></div>
    <div id="run" class="dot run"></div>
    <div id="toggle" @click="changeRun" class="trigger">
      <div class="innerDot"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "rightComponent",
  data () {
    return {
      activeRun: true
    }
  },
  methods: {
    changeRun() {
      this.activeRun = !this.activeRun
      this.updateVisual()
    },
    updateVisual() {
      document.getElementById('run').style.backgroundColor = this.activeRun ? 'green' : 'red'
      document.getElementById('toggle').style.paddingTop = this.activeRun ? '0.2em' : '0.9em'
    }
  }

}
</script>

<style scoped>
.innerDot {
  width: 0.7em;
  height: 0.7em;
  border-radius: 50%;
  background-color: black;
}

.trigger {
  width: 1em;
  height: 1.7em;
  border-radius: 30%;
  background-color: lightgray;
  margin-left:40%;
  margin-top: 15%;
  cursor: pointer;
  padding-top: 0.2%;

  justify-content: center;
  display: flex;
}

.dot {
  width: 0.8em;
  height: 0.5em;
  border-radius: 30%;
}
.pow {
  margin-top: 21.9%;
  margin-left: 68.9%;
  background-color: green;
}
.run {
  margin-top: 23.1%;
  margin-left: 68.9%;
  background-color: green;
}

.stack {
  display: grid;
}
.stack > * {
  grid-row: 1;
  grid-column: 1;
}
</style>