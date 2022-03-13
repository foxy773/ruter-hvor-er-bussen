<template>
  <div id="map" />
</template>

<script>
import mapboxgl from "mapbox-gl";
import "mapbox-gl/dist/mapbox-gl.css";

export default {

  data() {
      return {
        /* access_token: import.meta.env.VUE_APP_MAP_ACCESS_TOKEN, */
        access_token: "pk.eyJ1IjoiZm94eTc3MyIsImEiOiJjbDA5YTVmeGQwYmJ4M2JwOTE2cHdoa3FxIn0.JR2Lt1fPq50dA6VQHY1kig",
        center: [10.75, 59.91]
      };
    },

    mounted() {
      this.createMap()
    },

    methods: {
      async createMap() {
			  try {
          mapboxgl.accessToken = this.access_token;
          const map = new mapboxgl.Map({
          container: "map",
          style: "mapbox://styles/foxy773/cl09b1vk9009i14rorc4xfcqr",
          zoom: 10.6,
          center: this.center
        });
      } catch (err) {
        console.log("map error", err);
      }
    }
  }
}

</script>

<style>
	#map {
  		height: 100vh;
	}
</style>