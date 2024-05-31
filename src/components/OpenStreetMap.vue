<template>
  <div id="map"></div>
</template>

<script lang="ts">
import { defineComponent, onMounted } from "vue";
import L from "leaflet";
import "leaflet/dist/leaflet.css";

export default defineComponent({
  name: "OpenStreetMap",
  setup() {
    onMounted(() => {
      const map = L.map("map").setView([3.139, 101.6869], 13);

      L.tileLayer("https://tile.openstreetmap.org/{z}/{x}/{y}.png", {
        maxZoom: 19,
        attribution:
          '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>',
      }).addTo(map);
    });
  },
});
</script>

<style scoped>
#map {
  min-height: 400px;
  width: auto;
  border-radius: 12px;
  margin-top: 40px;
}

@media screen and (max-width: 993px){
  #map {
    margin-top: 20px;
  }
}
</style>
