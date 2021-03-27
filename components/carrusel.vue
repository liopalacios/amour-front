<template>
      <v-carousel hide-delimiters>
        <v-carousel-item
        v-for="(item,i) in items"
        :key="i"
        :src="item.src"
        reverse-transition="fade-transition"
        transition="fade-transition"
      ></v-carousel-item>
      </v-carousel>
</template>

<script>

export default {
  name: 'carrusel',
  data () {
    return {
      items: [
        {
          src: 'https://cdn.pixabay.com/photo/2016/09/22/15/42/roses-1687547__340.jpg'
        },
        {
          src: 'https://cdn.pixabay.com/photo/2017/05/06/14/13/pathway-2289978__340.jpg'
        },
        {
          src: 'https://cdn.pixabay.com/photo/2016/07/11/20/37/marguerite-1510602__340.jpg'
        },
        {
          src: 'https://cdn.pixabay.com/photo/2017/06/02/13/43/roses-2366341__340.jpg'
        }
      ]
    }
  }
}

</script>
