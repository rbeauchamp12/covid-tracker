<template>
  <div class="home">
    Hello World 
  </div>
</template>

<script>


export default {
  name: 'Home',
  components: {},
  data() {
    return {
      loading: true,
      title: 'Global',
      dateDate: '',
      stats: {},
      countries: [],
      loadingImage: require('../assets/hourglass.gif')
  }
},
  methods: {
    async fetchCovidData() {
      const res = await fetch('https://www.covid19api.com/summary')
      const data = await res.json()
      return data
      },
  },
  async created() {
    const data = await this.fetchCovidData()
  },
}
</script>
