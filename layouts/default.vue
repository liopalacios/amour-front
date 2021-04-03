<template>
  <v-app dark>
  <v-main>
    <v-card class="overflow-hidden">
      <v-app-bar
        absolute
        color="#FF5050"
        dark
        shrink-on-scroll
        src="https://cdn.pixabay.com/photo/2014/06/22/05/49/red-374318_1280.jpg"
        scroll-target="#scrolling-techniques-5"
        scroll-threshold="500"
      >
        <template v-slot:img="{ props }">
          <v-img
            v-bind="props"
            gradient="to top right, rgba(241, 103, 103 ,.7), rgba(241, 103, 103 ,.7)"
          ></v-img>
        </template>

          <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

        <v-app-bar-title>Shopping-amour &nbsp; &nbsp; &nbsp;</v-app-bar-title>

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

        <template v-slot:extension>
          <v-tabs
            v-model="tabs"
            centered
          >
            <v-tab
              v-for="n in 3"
              :key="n"
            >
              Item {{ n }}
            </v-tab>
          </v-tabs>
        </template>

      </v-app-bar>

      <v-sheet
        id="scrolling-techniques-5"
        class="overflow-y-auto"
        max-height="94vh"
      >
        <v-container style="height: 100%;">
          <nuxt />
          <Footer/>
        </v-container>
      </v-sheet>
      </v-card>
        <div class="overflow-hidden">

          <v-bottom-navigation
            v-model="value"
            :input-value="active"
            color="indigo"
          >
            <v-btn>
              <span>Recents</span>

              <v-icon>mdi-history</v-icon>
            </v-btn>

            <v-btn>
              <span>Favorites</span>

              <v-icon>mdi-heart</v-icon>
            </v-btn>

            <v-btn>
              <span>Nearby</span>

              <v-icon>mdi-map-marker</v-icon>
            </v-btn>
          </v-bottom-navigation>
        </div>

         <v-navigation-drawer
        v-model="drawer"
        absolute
        bottom
        temporary
      >
        <v-list
          nav
          dense
        >
          <v-list-item-group
            v-model="group"
            active-class="deep-purple--text text--accent-4"
          >
            <v-list-item>
              <v-list-item-title>Foo</v-list-item-title>
            </v-list-item>

            <v-list-item>
              <v-list-item-title>Bar</v-list-item-title>
            </v-list-item>

            <v-list-item>
              <v-list-item-title>Fizz</v-list-item-title>
            </v-list-item>

            <v-list-item>
              <v-list-item-title>Buzz</v-list-item-title>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-navigation-drawer>
    </v-main>
  </v-app>
</template>

<script>
import Footer from '~/components/footer.vue'
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      value: 1,
      active: true,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
      Footer
    }
  }
}
</script>
