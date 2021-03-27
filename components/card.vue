<template>
  <v-container fluid>
      <v-row dense>
        <v-col
          v-for="card in cards"
          :key="card.title"
          :cols="card.flex"
        >
          <v-card>
            <v-img
              :src="card.src"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="200px"
            >
              <v-card-title v-text="card.title"></v-card-title>
            </v-img>
            <v-card-text>
              <h3>Ramo Armonía Floral &nbsp;<b>S/ 135.20</b></h3>
            </v-card-text>
            <v-card-actions>
              <v-btn
                class="ma-2"
                color="success"
                dark
              >
                <v-icon
                  dark
                  right
                >
                  mdi-basket-plus
                </v-icon>
                Agregar
              </v-btn>
              <v-spacer></v-spacer>

              <v-btn
                class="ma-2"
                color="danger">
                <v-icon
                  danger
                    right
                  >mdi-heart</v-icon>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
</template>

<script>
export default {
  data: () => ({
    cards: [
      { title: 'Rosas', src: 'https://cdn.pixabay.com/photo/2016/11/23/17/56/wedding-1854074__340.jpg' },
      { title: 'Best airlines', src: 'https://cdn.pixabay.com/photo/2016/05/13/17/16/letter-1390463__340.jpg' }
    ]
  })
}
</script>
