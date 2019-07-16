<template>
  <div>
    <city-header></city-header>
  </div>
</template>
<script>
import CityHeader from './components/Header'
import axios from 'axios'
export default {
  name: 'City',
  components: {
    CityHeader
  },
  data () {
    return {
      hotCities: {},
      cities: []
    }
  },
  methods: {
    getCityInfo () {
      axios.get('http://localhost:8080/static/mock/city.json')
        .then(this.getCityInfoSucc)
    },
    getCityInfoSucc (res) {
      res = res.date
      if (res.ret && res.data) {
        const data = res.data
        this.hotCities = data.hotCities
        this.cities = data.cities
      }
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>
<style lang="stylus" scoped>

</style>
