<template>
  <div :class="{ 'principal': true, 'disable-overflow': true }">
    <div v-show="overlay" class="overlay-image">
      <div class="container imagem">
        <img :src="image" alt="">
      </div>
      <div class="icon">
        <a href="#" @click="overlay = false"><i data-feather="x"></i></a>
      </div>
    </div>
    <nav-top />

    <div class="container thumbnails fade">
      <div class="thumb"><img v-lazy="'/images/low/1.png'" alt="" class="img-fluid opacity" @click="enableOverlay('/images/high/1.png')"></div>
      <div class="thumb"><img v-lazy="'/images/low/2.png'" alt="" class="img-fluid opacity" @click="enableOverlay('/images/high/2.png')"></div>
      <div class="thumb"><img v-lazy="'/images/low/3.png'" alt="" class="img-fluid opacity" @click="enableOverlay('/images/high/3.png')"></div>
      <div class="thumb"><img v-lazy="'/images/low/4.png'" alt="" class="img-fluid opacity" @click="enableOverlay('/images/high/4.png')"></div>
      <div class="thumb"><img v-lazy="'/images/low/5.png'" alt="" class="img-fluid opacity" @click="enableOverlay('/images/high/5.png')"></div>
      <div class="thumb"><img v-lazy="'/images/low/6.png'" alt="" class="img-fluid opacity" @click="enableOverlay('/images/high/6.png')"></div>
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
    background: rgba(255, 255, 255, 0.9);
    height: 100%;
    width: 100%;
    position: fixed;

    display: flex;
    justify-content: center;
    align-items: center;

    padding: 20px;
}
.principal .overlay-image .imagem {
  max-height: 100%;
  height: 100%;

  display: flex;
  justify-content: center;
  align-items: center;
}
.principal .overlay-image .imagem img {
  height: 100%;
}
.principal .overlay-image .icon {
  /* margin-left: auto; */
  padding-right: 20px;
  margin-bottom: auto;
}
.principal .feather {
  stroke: #999;
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
  },
  mounted() {
    if (process.browser) {
        $(function () {
            feather.replace()
        })
    }
  }
}
</script>

