<template>
  <div class="home">
    <div id="map"></div>
  </div>
</template>

<style>
  #map {
    height: 700px;
    width: 100%;
  }
</style>

<script>
/* global mapboxgl */
export default {
  mounted: function() {
    mapboxgl.accessToken = process.env.VUE_APP_MAPBOX_ACCESS_TOKEN;
    new mapboxgl.Map({
      container: 'map', // container id
      style: 'mapbox://styles/mapbox/streets-v11', // style URL
      center: [-87.623177, 41.881832], // starting position [lng, lat]
      zoom: 11 // starting zoom
    });
  }
};
</script>
