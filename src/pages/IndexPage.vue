<script setup>
import { ref, watch } from 'vue';
import { GoogleMap, Marker, InfoWindow } from 'vue3-google-map';

const center = { lat: -25.363, lng: 131.044 };
const infowindow = ref(true); // Will be open when mounted

watch(infowindow, (v) => {
  alert('infowindow has been ' + (v ? 'opened' : 'closed'));
});
</script>

<template>
<div>
asdass

  <GoogleMap
    api-key="AIzaSyAj4VqWs_qq9pYVdl3kYCgy5bUIShMMskQ"
    style="width: 100%; height: 500px"
    :center="center"
    :zoom="4"
  >
    <Marker :options="{ position: center }">
      <InfoWindow v-model="infowindow">
        <div id="content">This is the infowindow content</div>
      </InfoWindow>
    </Marker>
  </GoogleMap>
  </div>
</template>


//AIzaSyAj4VqWs_qq9pYVdl3kYCgy5bUIShMMskQ