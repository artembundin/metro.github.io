<template>
  <div id="app" v-if="linesData && stationsData">
    <MetroMap/>
    <ChildComponent :stations="stationsData" :lines="linesData" />
  </div>
</template>

<script>
import ChildComponent from './components/ChildComponent.vue'
import metroData from './'



export default {
  components: {
    ChildComponent,
  },
  data() {
    return {
      stationsData: [],
      linesData: [],
    }
  },
  created() {
    console.log(metroData)
    console.log(metroData.lines)
    this.linesData = metroData.lines
    this.stationsData = metroData.stations
  }
}
</script>