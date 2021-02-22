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
/* global mapboxSdk */
export default {
  data: function() {
    return {
      places: [
        { lat: -25.363, lng: 131.044, description: "A place in Australia" },
        { lat: -33.8675, lng: 151.207, description: "The main city!" },
      ],
    };
  },
  mounted: function() {
    mapboxgl.accessToken = process.env.VUE_APP_MAPBOX_ACCESS_TOKEN;
    var map = new mapboxgl.Map({
      container: "map", // container id
      style: "mapbox://styles/mapbox/streets-v11", // style URL
      center: [-87.623177, 41.881832], // starting position [lng, lat]
      zoom: 11, // starting zoom
    });

    this.places.forEach((place) => {
      console.log(place);
      // create the popup
      var popup = new mapboxgl.Popup({ offset: 25 }).setText(place.description);
      // create the marker
      new mapboxgl.Marker()
        .setLngLat([place.lng, place.lat])
        .setPopup(popup) // sets a popup on this marker
        .addTo(map);
    });
    // var mapboxClient = mapboxSdk({ accessToken: mapboxgl.accessToken });
    // mapboxClient.geocoding
    //   .forwardGeocode({
    //     query: "Bobs Donuts San Francisco",
    //     autocomplete: false,
    //     limit: 1,
    //   })
    //   .send()
    //   .then(function(response) {
    //     if (
    //       response &&
    //       response.body &&
    //       response.body.features &&
    //       response.body.features.length
    //     ) {
    //       var feature = response.body.features[0];

    //       var map = new mapboxgl.Map({
    //         container: "map",
    //         style: "mapbox://styles/mapbox/streets-v11",
    //         center: feature.center,
    //         zoom: 10,
    //       });
    //       new mapboxgl.Marker().setLngLat(feature.center).addTo(map);
    //     }
    //   });
  },
};
</script>
