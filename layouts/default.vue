<template>
  <v-app dark>
  <v-main>
    <v-card class="overflow-hidden">
      <!-- shrink-on-scroll -->
      <v-app-bar
        absolute
        color="#FF5050"
        dark

        src="https://cdn.pixabay.com/photo/2014/06/22/05/49/red-374318_1280.jpg"
        scroll-target="#scrolling-techniques-5"
        scroll-threshold="300"
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
            fixed-tabs
          >

            <v-tabs-slider></v-tabs-slider>

            <v-menu :close-on-content-click="false" open-on-hover bottom offset-y style="position: static;">
              <template v-slot:activator="{ on }">
                <v-tab
                    class="primary--white"
                  dark
                  v-on="on"
                >
                    <v-icon>mdi-phone</v-icon>
                </v-tab>
              </template>

              <v-list  style=" width: 100% !important; left: 0 !important; right: 0 !important; padding: 15px !important;">
                <v-row
                    align="center"
                    justify="space-around"
                  >
                    <v-col cols="5" sm="5" md="5">
                      ssss
                    </v-col>
                    <v-col cols="7" sm="7" md="7">
                                <v-list-group
                                style="padding: 10px !important;"
                                  v-for="item in items2"
                                  :key="item.title"
                                  v-model="item.active"
                                  :prepend-icon="item.action"
                                  no-action
                                >
                                  <template v-slot:activator  >
                                    <v-container>
                                          <v-list-tile>
                                              <v-list-tile-title><v-icon>{{ item.icon }}</v-icon> {{ item.title }} </v-list-tile-title>
                                          </v-list-tile>
                                    </v-container>
                                  </template>
                                </v-list-group>
                    </v-col>
                </v-row>
              </v-list>

            </v-menu>

            <v-tab
              href="#mobile-tabs-5-1"
              class="primary--white"
            >
              <v-icon>mdi-phone</v-icon>
            </v-tab>

            <v-tab
              href="#mobile-tabs-5-2"
              class="primary--white"
            >
              <v-icon>mdi-heart</v-icon>
            </v-tab>

            <v-tab
              href="#mobile-tabs-5-3"
              class="primary--white"
            >
              <v-icon>mdi-account-box</v-icon>
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
      Footer,
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
      items2: [
        {
          action: 'local_activity',
          icon: 'fas fa-lock',
          title: 'Opciones'
        },
        {
          action: 'restaurant',
          title: 'Opciones 1'
        },
        {
          action: 'restaurant',
          title: 'Opciones 2'
        }
      ]
    }
  }
}
</script>
