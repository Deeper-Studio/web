<template>
<!--  <div style="margin-top: 40px">-->
    <!--    <side-menu id="side-menu"></side-menu>-->
<!--  <el-container class="home-container">-->
<!--    <el-header>-->
<!--      <MainSearch></MainSearch>-->
<!--    </el-header>-->
<!--    <el-main>-->
<!--      <Carousel></Carousel>-->
<!--    </el-main>-->
<!--    <el-footer>-->
<!--      <slogan id="slogan"></slogan>-->
<!--      <about id="about"></about>-->
<!--    </el-footer>-->
<!--  </el-container>-->
  <div>
    <div><MainSearch></MainSearch></div>
    <div><Carousel></Carousel></div>
    <div><Authors></Authors></div>
    <div>
      <slogan id="slogan"></slogan>
      <about id="about"></about>
    </div>
  </div>
<!--  </el-container>-->
<!--  &lt;!&ndash;        <div id="header-div">&ndash;&gt;-->
<!--  <div style="height: 150px"></div>-->
<!--    </div>-->
</template>

<script>
  import About from '../common/About'
  import MyCarousel from './MyCarousel'
  import Slogan from './Slogan'
  import Carousel from './Carousel'
  import MainSearch from './MainSearch'
  import Authors from './Authors'
  export default {
    name: 'AppIndex',
    components: {Authors, MainSearch, MyCarousel, Carousel, Slogan, About}
  }
</script>

<style scoped>
  .el-header {
    /*background-color: #B3C0D1;*/
    /*color: #333;*/
    text-align: center;
    line-height: 60px;
  }
  .el-main {
    /*background-color: #E9EEF3;*/
    /*color: #333;*/
    text-align: center;
    line-height: 160px;
  }
  .el-footer {
    text-align: center;
    line-height: 60px;
  }
  .main {
    width: 800px;
    height: 100px;
    margin-left: auto;
    margin-right: auto;
    margin-top: 10px;
  }
  .home-container{
    height: 100%;
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
