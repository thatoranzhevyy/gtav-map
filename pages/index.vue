<template>
    <div id="map-wrap">
      <client-only>
        <l-map
          class="map"
          :zoom="zoom"
          :center="center"
          :minZoom="minZoom"
          :maxZoom="maxZoom"
          :maxBounds="maxBounds"
          :options="{zoomControl: false}"
          @update:zoom="zoomUpdated"
          @update:center="centerUpdated"
          @click="addMarker"
        >
          <l-control-layers position="topright"></l-control-layers>
          <l-control-zoom position="topright"></l-control-zoom>
          <l-tile-layer
            v-for="tileProvider in tileProviders"
            :key="tileProvider.name"
            :name="tileProvider.name"
            :visible="tileProvider.visible"
            :url="tileProvider.url"
            layer-type="base"></l-tile-layer>
          <icones
            v-for="(marker, index) in markers"
            :key="marker.id"
            :marker="marker"
            @click="removeMarker(index)"
          >
          </icones>
        </l-map>
      </client-only>
    </div>
</template>

<script>
import {latLngBounds, latLng} from "leaflet";
import 'leaflet/dist/leaflet.css';

export default {
  data() {
    return {
      tileProviders: [
        {
          name: 'Спутник',
          visible: true,
          url: 'https://gtav-map.netlify.app/tiles/satellite/{z}-{x}_{y}.png',
        },
        {
          name: 'Атлас',
          visible: false,
          url: 'https://gtav-map.netlify.app/tiles/atlas/{z}-{x}_{y}.png',
        },
        {
          name: 'Дорога',
          visible: false,
          url: 'https://gtav-map.netlify.app/tiles/road/{z}-{x}_{y}.png',
        },
      ],
      url: 'https://gtav-map.netlify.app/tiles/road/{z}-{x}_{y}.png',
      center: [61.61385787081098, -124.4374303892255],
      maxBounds: latLngBounds([
        [50.77815527465925, -59.15039062500001],
        [85.04923290826919, -179.98901367187503]
      ]),
      zoom: 5,
      minZoom: 3,
      maxZoom: 7,
      markers: [
        // {
        //   id: 1,
        //   imageUrl: 'https://img.icons8.com/material/24/000000/us-dollar-circled--v1.png',
        //   coordinates: [63.966318784384256, -130.42968750000003]
        // },
        // {
        //   id: 2,
        //   imageUrl: 'https://img.icons8.com/material/24/000000/car.png',
        //   coordinates: [61.386197865704695, -123.37646484375001]
        // },
        // {
        //   id: 3,
        //   imageUrl: 'https://img.icons8.com/material/24/000000/police-car--v1.png',
        //   coordinates: [59.366793908532124, -133.08837890625003]
        // },
        // {
        //   id: 4,
        //   imageUrl: 'https://img.icons8.com/material/24/000000/shopping-cart--v1.png',
        //   coordinates: [62.2679226294176, -118.25683593750001]
        // },
        // {
        //   id: 5,
        //   imageUrl: 'https://img.icons8.com/material/24/000000/hospital.png',
        //   coordinates: [59.33318942659219, -122.67333984375001]
        // },
      ]
    }
  },
  methods: {
    zoomUpdated(zoom) {
      this.zoom = zoom;
    },
    centerUpdated(center) {
      this.center = center;
    },
    addMarker(event) {
      // this.markers.push(event.latlng);
      this.markers.push({
        imageUrl: 'https://img.icons8.com/material/24/000000/marker.png',
        coordinates: event.latlng
      });
    },
    removeMarker(index) {
      this.markers.splice(index, 1);
    },
  }
}
</script>

<style>
.map {
  width: 100%;
  height: 100%;
  overflow: hidden
}
</style>
