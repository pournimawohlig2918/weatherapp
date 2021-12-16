<template>
  <div>
    <h1 class="main-heading text-center">Weather App</h1>
    <v-parallax
      class="back-image"
      src="https://images.pexels.com/photos/3783385/pexels-photo-3783385.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940"
    >
      <v-col cols="12" sm="6" md="6">
        <v-text-field class="center" filled rounded dense></v-text-field>
      </v-col>
    </v-parallax>
  </div>
</template>

<script>
export default {
  // name: 'IndexPage',
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
  
