<template>
  <div style="margin-top: 40px">
<!--    <side-menu id="side-menu"></side-menu>-->
      <div class="home">
<!--        <div id="header-div">-->
          <div style="height: 150px"></div>
          <Carousel></Carousel>
<!--          <quick-nav style="float: right;margin-top: -450px;margin-right: 480px"></quick-nav>-->
<!--        </div>-->
<!--        <update-card id="update-card"></update-card>-->
        <slogan id="slogan"></slogan>
        <about id="about"></about>
      </div>
  </div>
</template>

<script>
  import About from '../common/About'
  import MyCarousel from './MyCarousel'
  import Slogan from './Slogan'
  import Carousel from './Carousel'
  export default {
    name: 'AppIndex',
    components: {MyCarousel, Carousel, Slogan, About}
  }
</script>

<style scoped>
  .home {
    width: 1150px;
    margin-left: auto;
    margin-right: auto;
    margin-top: -20px;
  }

  #header-div {
    padding-bottom: 20px;
    padding-left: 5px;
    background-color: white;
  }

  #side-menu {
    position: fixed;
    margin-left: 50%;
    left: -680px;
    top: 100px;
  }
</style>
