<template>
  <div id="mapid"></div>
</template>

<script>
import '@/leaflet/style/leaflet.css';
import * as L from '@/leaflet/Leaflet.js'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      map: null
    }
  },
  mounted () {
    this.map = L.map('mapid', {
        center: [32, 112],
        zoom: 8
    });
    const lear = L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
    });
    lear.addTo(this.map);
    // var a = {name: '1212', age: 12};
    // a.addM = function () {
    //   console.log(this);
    // }
    // a.addM()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#mapid {
  width: 500px;height: 300px;margin: 20px;
  border: 1px solid red
}
</style>
