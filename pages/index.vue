<template>
  <div class="principal">
    <nav-top />

    <div class="container thumbnails fade">
      <div class="thumb"><img src="/images/1.png" alt="" class="img-fluid opacity"></div>
      <div class="thumb"><img src="/images/2.png" alt="" class="img-fluid opacity"></div>
      <div class="thumb"><img src="/images/3.png" alt="" class="img-fluid opacity"></div>
      <div class="thumb"><img src="/images/4.png" alt="" class="img-fluid opacity"></div>
      <div class="thumb"><img src="/images/5.png" alt="" class="img-fluid opacity"></div>
      <div class="thumb"><img src="/images/6.png" alt="" class="img-fluid opacity"></div>
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

  background: #2d3436;
  padding: 20px;
  text-transform: uppercase;
  color: #fff;
}
</style>
<script>
import navTop from '@/components/nav'

export default {
    components: {
      navTop
    }
}
</script>

