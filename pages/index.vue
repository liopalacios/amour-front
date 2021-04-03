<template>
  <v-row  align="center">
      <v-col cols="12">
        <br>
        <br>
        <br>
        <br>
        <br>
      <Carrusel/>
      </v-col>
      <v-col cols="12" sm="6" md="4">
        <card/>
      </v-col>
      <v-col cols="12" sm="6" md="4">
        <card/>
      </v-col>
      <v-col cols="12" sm="6" md="4">
        <card/>
      </v-col>
      <v-col cols="12" sm="6" md="4">
        <card/>
      </v-col>
  </v-row>
</template>

<script>
import Carrusel from '~/components/carrusel.vue'
import Card from '~/components/card.vue'
export default {
  components: {
    Carrusel,
    Card
  }
}
</script>
