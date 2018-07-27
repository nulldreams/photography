<template>
  <div :class="{ 'principal': true, 'disable-overflow': true }">
    <div v-if="overlay" class="overlay-image">
      <div class="container imagem">
        <img class="img-fluid" :src="image" alt="">
      </div>
    </div>
    <nav-top />
    <div class="container thumbnails fade">
      <div class="thumb"><img v-lazy="'/images/1.png'" alt="" class="img-fluid opacity" @click="enableOverlay('/images/1.png')"></div>
      <div class="thumb"><img v-lazy="'/images/2.png'" alt="" class="img-fluid opacity" @click="enableOverlay('/images/2.png')"></div>
      <div class="thumb"><img v-lazy="'/images/3.png'" alt="" class="img-fluid opacity" @click="enableOverlay('/images/3.png')"></div>
      <div class="thumb"><img v-lazy="'/images/4.png'" alt="" class="img-fluid opacity" @click="enableOverlay('/images/4.png')"></div>
      <div class="thumb"><img v-lazy="'/images/5.png'" alt="" class="img-fluid opacity" @click="enableOverlay('/images/5.png')"></div>
      <div class="thumb"><img v-lazy="'/images/6.png'" alt="" class="img-fluid opacity" @click="enableOverlay('/images/6.png')"></div>
    </div>

    <div class="spacer container all-projects">
      <a href="#">See all projects</a>
    </div>
  </div>
</template>
<style>
.principal .thumbnails {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: row;
  flex-wrap: wrap;

  opacity: 0;
}
.principal .thumbnails > .thumb {
  width: 33%;
  padding: 25px;
}
.principal .all-projects {
  display: flex;
  justify-content: center;
  align-items: center;
}
.principal .all-projects a {
  font-family: 'Montserrat', sans-serif;
  font-weight: 500;

  background: #795548;
  padding: 20px;
  text-transform: uppercase;
  color: #fff;
}
.principal .overlay-image {
    z-index: 10;
    background: rgba(25, 25, 25, .8);
    height: 100vh;
    width: 100vw;
    position: absolute;

    display: flex;
    justify-content: center;
    align-items: center;
}
.principal .overlay-image .imagem {
  width: 40%;
}
</style>
<script>
import navTop from '@/components/nav'

export default {
  data () {
    return {
      overlay: false,
      image: ''
    }
  },
  components: {
    navTop
  },
  methods: {
    enableOverlay: function (image) {      
      if (process.browser)  {

        this.overlay = true        
        $('body').addClass('disable-overflow')
        this.image = image
      }
    }
  }
}
</script>

