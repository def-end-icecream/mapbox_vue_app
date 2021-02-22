<template>
  <div class="home">
    <div id="map"></div>
  </div>
</template>

<style>
  body {
    margin: 0;
    padding: 0;
  }

  #map {
    position: absolute;
    top: 0;
    bottom: 0;
    width: 100%;
  }
</style>

<script>
/* global mapboxgl */
export default {
  mounted: function() {
    mapboxgl.accessToken = 'your-access-token';
    new mapboxgl.Map({
      container: 'map', // container id
      style: 'mapbox://styles/mapbox/streets-v11', // style URL
      center: [-122.446747, 37.733795], // starting position [lng, lat]
      zoom: 11 // starting zoom
    });
  }
};
</script>
