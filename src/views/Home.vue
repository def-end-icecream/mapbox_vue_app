<template>
  <div class="home">
    <div id="map"></div>
  </div>
</template>

<style>
  #map {
    top: 0;
    bottom: 0;
    height: 700px;
    width: 100%;
  }
</style>

<script>
/* global mapboxgl */
export default {
  mounted: function() {
    mapboxgl.accessToken = 'pk.eyJ1IjoiZHphZ2hpYW4iLCJhIjoiY2pzbnF0NmV0MGY2czQzbXBpMjcwMzRmNiJ9.Jei4-17Vu7hJSerisjPCEg';
    new mapboxgl.Map({
      container: 'map', // container id
      style: 'mapbox://styles/mapbox/streets-v11', // style URL
      center: [-87.623177, 41.881832], // starting position [lng, lat]
      zoom: 11 // starting zoom
    });
  }
};
</script>
