<template>
  <v-app dark>
  <v-main>
    <v-card class="overflow-hidden">
      <v-app-bar
        absolute
        color="#FF5050"
        dark
        shrink-on-scroll
        prominent
        src="https://cdn.pixabay.com/photo/2014/06/22/05/49/red-374318_1280.jpg"
        fade-img-on-scroll
        scroll-target="#scrolling-techniques-5"
        scroll-threshold="500"
      >
        <template v-slot:img="{ props }">
          <v-img
            v-bind="props"
            gradient="to top right, rgba(241, 103, 103 ,.7), rgba(241, 103, 103 ,.7)"
          ></v-img>
        </template>
<!--
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
-->
        <v-app-bar-title>Shopping-amour</v-app-bar-title>

        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>
        <v-btn icon>
          <v-icon>mdi-heart</v-icon>
        </v-btn>
        <v-btn icon>
          <v-icon>mdi-basket</v-icon>
        </v-btn>

      </v-app-bar>
      <v-sheet
        id="scrolling-techniques-5"
        class="overflow-y-auto"
        max-height="100vh"
      >
        <v-container style="height: 100%;">
          <nuxt />
        </v-container>
      </v-sheet>
    </v-card>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>
