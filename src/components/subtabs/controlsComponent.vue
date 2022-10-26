<template>
  <div class="mb-4 flex flex-col">
    <div class="flex justify-center">
      <button @click="setObject" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        {{object ? 'Remove Object' : 'Set Object'}}
      </button>
    </div>
    <div class="flex justify-center">
      <button @mousedown="setTasterOne" @mouseup="setTasterOne">
        <div class="h-10 w-10 mt-4 ml-1 mr-1" style="border-radius: 50%">
          <p class='text-black'   :class="tasterOne ? 'bg-red-700' : 'bg-red-400'">T1</p>
        </div>
      </button>

      <button @mousedown="setTasterTwo" @mouseup="setTasterTwo">
        <div class="h-10 w-10 mt-4 ml-1 mr-1" style="border-radius: 50%">
          <p class='text-black'   :class="tasterTwo ? 'bg-red-700' : 'bg-red-400'">T2</p>
        </div>
      </button>

      <button @click="setButtonOne">
        <div class="h-10 w-10 mt-4 ml-1 mr-1" style="border-radius: 50%">
          <p class='text-black'   :class="buttonOne ? 'bg-red-700' : 'bg-red-400'">K1</p>
        </div>
      </button>

      <button @click="setButtonTwo">
        <div class="h-10 w-10 mt-4 ml-1 mr-1" style="border-radius: 50%">
          <p class='text-black'   :class="buttonTwo ? 'bg-red-700' : 'bg-red-400'">K2</p>
        </div>
      </button>

      <div class=" flex justify-center flex-col">
        <CircleSlider
            v-model="sliderValue"
            :value="sliderValue"
            :side="100"
            :min="0"
            :max="10"
            :step-size="0.5"
            :circle-width-rel="20"
            :progress-width-rel="10"
            :knob-radius="10"
            knob-color="#1D4ED8"
            @update="setSliderValue"
            progress-color="#3482F6"/>
          <div class="ml-10 text-blue-700">{{sliderValue.toFixed(1) + ' V'}}</div>
      </div>

    </div>
  </div>
</template>

<script>
import CircleSlider from "@/components/custom-component/CircleSlider";
export default {
  components: {
    CircleSlider
  },
  name: "ControlsComponent",
  data() {
    return {
      object: false,
      tasterOne: false,
      tasterTwo: false,
      buttonOne: false,
      buttonTwo: false,
      sliderValue: 0,
    }
  },
  methods: {
    setObject() {
      this.object = !this.object
    },
    setButtonOne() {
      this.buttonOne = !this.buttonOne
    },
    setButtonTwo() {
      this.buttonTwo = !this.buttonTwo
    },
    setTasterOne() {
      this.tasterOne = !this.tasterOne
    },
    setTasterTwo() {
      this.tasterTwo = !this.tasterTwo
    },
    setSliderValue(value) {
      this.sliderValue = value
    }
  }
}
</script>

<style scoped>

</style>