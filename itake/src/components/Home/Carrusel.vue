<template>
  <div>
    <b-container fluid class="text-center">
      <h1>Bienvenidos</h1>
    <b-carousel id="carrusel"
      v-model="slide"
      :interval="4000"
      fade
      indicators
      background="#ababab"
      img-width="1024"
      img-height="480"
      style="text-shadow: 1px 1px 2px #333;"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <!-- Text slides with image -->
      <b-carousel-slide
        caption="First slide"
        text="Nulla vitae elit libero, a pharetra augue mollis interdum."
        img-src="https://images.pexels.com/photos/1276553/pexels-photo-1276553.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940"
      ></b-carousel-slide>

      <!-- Slides with custom text -->
      <b-carousel-slide img-src="https://images.unsplash.com/photo-1587135672368-c47f813ccf0f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80">
        <h1>¡Bienvenidos a iTake!</h1>
        <b-button variant="primary"><router-link to="/busqueda">¡Adopta una mascota!</router-link></b-button>
      </b-carousel-slide>

      <!-- Slides with image only -->
      <b-carousel-slide img-src="https://images.unsplash.com/photo-1513360371669-4adf3dd7dff8?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=750&q=80"></b-carousel-slide>

      <!-- Slides with img slot -->
      <!-- Note the classes .d-block and .img-fluid to prevent browser default image alignment -->
      <b-carousel-slide>
        <template v-slot:img>
          <img
            class="d-block img-fluid w-100"
            width="500"
            height="400"
            src="https://images.pexels.com/photos/57627/pexels-photo-57627.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940"
            alt="image slot"
          >
        </template>
      </b-carousel-slide>
    </b-carousel>
    </b-container>
  </div>

  
</template>

<script>
  export default {
 name: "Carrusel",
    data() {
      return {
        slide: 0,
        sliding: null
      }
    },
    methods: {
      onSlideStart(slide) {
        this.sliding = true
      },
      onSlideEnd(slide) {
        this.sliding = false
      }
    }
  }
</script>


