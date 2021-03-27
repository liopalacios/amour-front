<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <!--<div class="text-center">
        <logo />
        <vuetify-logo />
      </div>-->
      <card/>
      <card/>
      <card/>
    </v-col>
  </v-row>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'
import Card from '~/components/card.vue'
export default {
  components: {
    Logo,
    VuetifyLogo,
    Card
  }
}
</script>
