<template>
    <Mapbox
        :access-token="accessToken"
        :map-options="mapOptions()"
        :geolocate-control="{
            show: true,
            position: 'top-right'
        }"
        :scale-control="{
            show: true,
            position: 'top-left'
        }"
        :fullscreen-control="{
            show: true,
            position: 'top-left'
        }">
    </Mapbox>
</template>

<script>
import { mapGetters } from 'vuex'
import Mapbox from 'mapbox-gl-vue';

export default {
    components: {
        Mapbox,
    },
    data: () => ({
        accessToken: 'pk.eyJ1IjoicmxlbWJvIiwiYSI6ImNqcG9kYmpkdjA3OXAzeHJ0YXpyY3F3amEifQ.bRtN1Fg_KAVXnhRspshrpA',
        mapStyle: 'mapbox://styles/mapbox/streets-v10',
        zoom: 13
    }),
    computed: {
        ...mapGetters({
            coordinates: 'restaurants/coordRestaurantSelected',
        }),
    },
    methods: {
        mapOptions() {
            return {
                style: this.mapStyle,
                center: this.coordinates,
                zoom: this.zoom,
            }  
        }
    },
}
</script>

<style>
#map {
    height: 450px;
    /* width: 100%; */
    top:0; 
    bottom:0;
}

canvas.mapboxgl-canvas {
    width: 100% !important;
}
</style>
