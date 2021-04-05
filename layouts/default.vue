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

        <v-spacer></v-spacer>
            <v-menu :close-on-content-click="false" open-on-hover bottom offset-y style="position: static;">
              <template v-slot:activator="{ on }" >
                <v-tab
                    class="primary--white"
                  dark
                  v-on="on"
                >
                    <v-icon>mdi-phone</v-icon>
                </v-tab>
              </template>

              <v-list style="position: relative !important;width: 100% !important; left: 0 !important; right: 0 !important; padding: 15px !important;">

                <v-row>
                    <v-col cols="4" sm="12" md="4">
                                <v-list-group
                                  v-for="item in items2"
                                  :key="item.title"
                                  v-model="item.active"
                                  :prepend-icon="item.action"
                                  no-action
                                >
                                  <template v-slot:activator  >
                                    <v-container>
                                          <v-list-tile>
                                             <v-icon>{{ item.icon }}</v-icon> <v-list-tile-title>&nbsp;&nbsp; {{ item.title }} ssssddddddddddddddddddddd</v-list-tile-title>
                                          </v-list-tile>
                                    </v-container>
                                  </template>
                                </v-list-group>
                    </v-col>
                    <v-col cols="4" sm="12" md="4">
                      ssssdddddddddddddddddddddeeeeeeeeeeeeeeeeeeeeee
                    </v-col>
                    <v-col cols="4" sm="12" md="4">
                                <v-list-group
                                  v-for="item in items2"
                                  :key="item.title"
                                  v-model="item.active"
                                  :prepend-icon="item.action"
                                  no-action
                                >
                                  <template v-slot:activator  >
                                    <v-container>
                                          <v-list-tile>
                                             <v-icon>{{ item.icon }}</v-icon> <v-list-tile-title>&nbsp;&nbsp; {{ item.title }} ssssddddddddddddddddddddd</v-list-tile-title>
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
              <v-icon>fas fa-search</v-icon>
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

        <v-spacer></v-spacer>
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
import '@fortawesome/fontawesome-free/css/all.css'
export default {
  data () {
    return {
      icons: {
        iconfont: 'mdiSvg' // 'mdi' || 'mdiSvg' || 'md' || 'fa' || 'fa4' || 'faSvg'
      },
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
          icon: 'fas fa-lock',
          title: 'Opciones'
        },
        {
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
