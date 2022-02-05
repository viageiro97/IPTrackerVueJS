<template>
  <div id="map">
    <l-map :zoom="zoom" :center="center">
      <l-tile-layer :url="url" :attribution="attribution"></l-tile-layer>
      <l-control-zoom position="bottomright"></l-control-zoom>
      <l-circle-marker :lat-lng="center" :radius="40" color="blue" />
    </l-map>
  </div>
</template>

<script>
import L from "leaflet";
import { LMap, LTileLayer, LControlZoom, LCircleMarker } from "vue2-leaflet";

export default {
  components: {
    LMap,
    LTileLayer,
    LControlZoom,
    LCircleMarker,
  },
  props: {
    zoom: Number,
    center: Array,
  },
  data() {
    return {
      url: "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
      attribution:
        '&copy; <a target="_blank" href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      bounds: null,
      icon: L.icon({
        iconUrl: "https://img.icons8.com/office/16/000000/place-marker--v1.png",
        iconSize: [32, 37],
        iconAnchor: [16, 37],
      }),
    };
  },
  methods: {},
};
</script>

<style scoped>
#map {
  z-index: 0;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>
