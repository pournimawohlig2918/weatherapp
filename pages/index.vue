<template>
  <div>
    <h1 class="main-heading text-center">Weather App</h1>

    <v-parallax
      class="back-image"
      src="https://images.pexels.com/photos/3783385/pexels-photo-3783385.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940"
    >
      <v-row justify="center px-2 py-4">
        <v-col cols="12" sm="4" md="4">
          <v-text-field
            class="search-con"
            filled
            rounded
            dense
            placeholder="What City?"
            v-model="city"
          ></v-text-field>
          <v-button v-on:click="submit"> check weather </v-button>
        </v-col>
      </v-row>
      <v-row>
        <!-- v-for="item in list" :key"item.name" -->
        <!-- {{ item.cityname }} -->
        <!-- v-for="wet in weather" :key="wet" -->
        <v-list-item v-if="weather.weather">
          <v-list-item-content class="text-center py-15">
            <v-list-title class="headline">{{ weather.name }}</v-list-title>
            <v-list-title class="sub-headline">{{ weather.base }}</v-list-title>
            <v-list-title>Country: {{ weather.sys.country }}</v-list-title>
            <v-list-subtitle class="s1">{{
              weather.main.temp
            }}</v-list-subtitle>
            <v-list-subtitle class="s2">{{ weather.wind.deg }}</v-list-subtitle>

            <!-- <v-list-title class="degree-title">8 degree</v-list-title>
            <v-list-subtitle class="weather-type">Mostly Rainy</v-list-subtitle> -->
          </v-list-item-content>
        </v-list-item>
      </v-row>
    </v-parallax>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'index',

  data() {
    return {
      city: '',
      weather: [],
    }
  },
  methods: {
    async submit() {
      const res = await axios.get(
        `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=c0dfefbe982217fe68cb2587edbd32ff`
      )

      this.weather = res.data
      console.log('>>>>>>>>>>>', this.weather)
    },
  },
  // mounted() {
  //   axios
  //     .get(
  //       'api.openweathermap.org/data/2.5/weather?q=mumbai&appid=c0dfefbe982217fe68cb2587edbd32ff'
  //     )
  //     .then((res) => {
  //       this.list = res.data.data
  //       console.log(res.data.data)
  //     })
  // },
}
</script>

<style scoped>
* {
  padding: 0;
  margin: 0;
}
.back-image {
  /* background-size: 12; */
  background-image: cover;
}
</style>
  
