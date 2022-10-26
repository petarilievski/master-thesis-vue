<template>
  <div id="embeddedScene">
    <a-scene embedded  vr-mode-ui="enabled: false;" arjs>

<!--      <a-assets>-->
<!--        <img id="grid" src="../assets/border.png" />-->
<!--      </a-assets>-->

      <a-marker id="cite" type="pattern" url="marker/pt-cite.patt">
        <a-plane
            src="assets/plc.jpg"
            scale="7.3 7.3 7.3"
            rotation="-90 0 0"
            position="0 0 -3"
        >
        </a-plane>
        <a-sphere radius="0.10" color="red"></a-sphere>
      </a-marker>

<!--      <a-marker type="barcode" value="1" id="m1" registerevents>-->
<!--        <a-sphere radius="0.10" color="red"></a-sphere>-->
<!--      </a-marker>-->

<!--      <a-marker type="pattern" url="data/kanji.patt" id="baseMarker" >-->
<!--      </a-marker>-->

<!--      <a-entity id="camera" camera></a-entity>-->
    </a-scene>
  </div>
</template>

<script>
import '@ar-js-org/ar.js/aframe/build/aframe-ar'

export default {
  name: 'a-frame',
  data() {
    return {
      markerVisible: { m0: false, m1: false, m2: false, m3: false, m4: false }
    }
  },
  methods: {
    handleInitEvents () {
      for (let markerVisibleKey in this.markerVisible) {
        this.addEvents(markerVisibleKey)
      }
    },
    addEvents(m) {
      const marker = document.querySelector("#" + m)
      marker.addEventListener('markerFound', () => {
        const entity = document.querySelector('video')
        entity.play()
        this.markerVisible[m] = true
      })
      marker.addEventListener('markerLost', () => {
        const entity = document.querySelector('video')
        entity.pause()
        this.markerVisible[m] = false
      })
    },
    handleBody() {
    }
  },
  mounted () {
    // this.handleInitEvents()
    // this.handleBody()
  },
}
</script>
