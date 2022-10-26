<template>
  <div id="embeddedScene">
    <a-scene embedded  vr-mode-ui="enabled: false;" arjs="debugUIEnabled: false; detectionMode: mono_and_matrix; matrixCodeType: 3x3;">

      <a-assets>
        <img id="grid" src="../assets/border.png" />
      </a-assets>

      <a-marker type="barcode" value="0" id="m0" registerevents>
        <a-sphere radius="0.10" color="red"></a-sphere>
        <!-- this group rotates the cylinder to point at marker m1 -->
        <a-entity id="cylinderGroup"></a-entity>
      </a-marker>

      <a-marker type="barcode" value="1" id="m1" registerevents>
        <a-sphere radius="0.10" color="red"></a-sphere>
      </a-marker>

<!--      <a-marker type="pattern" url="/data" id="baseMarker" >-->
<!--      </a-marker>-->

<!--      <a-entity camera></a-entity>-->

      <a-entity run></a-entity>

    </a-scene>
  </div>
</template>

<script>
import '@ar-js-org/ar.js/aframe/build/aframe-ar'

export default {
  name: 'a-frame',
  methods: {
    handleVideo () {
      // const m = document.querySelector('a-marker#frac3')
      // m.addEventListener('markerFound', () => {
      //   const entity = document.querySelector('video')
      //   entity.play()
      //   console.log('found')
      // })
      // m.addEventListener('markerLost', () => {
      //   const entity = document.querySelector('video')
      //   entity.pause()
      //   console.log('lost')
      // })
    }
  },
  mounted () {
    this.handleVideo()
    const scene = document.querySelector('#embeddedScene')
    scene.style.width = '50%';
  },
  beforeCreate () {
    document.body.classList.add('arjs')
  },
  beforeUnmount () {
    location.reload()
  }
}
</script>

<style scoped>
a-scene { display: block; width: 50%; }

</style>
