<template>
  <el-card class="card-carousel">
  <el-carousel  class="push" :interval="4000" arrow="always">
    <el-carousel-item v-for="item in items" :key="item.id">
      <a :href=item.link target="_blank">
        <img :src=item.img alt="" class="carousel_img">
      </a>
<!--      问题2： 标题加不上-->
      <el-card class="title">
        <h3>{{item.title}}</h3>
      </el-card>
    </el-carousel-item>
  </el-carousel>
  </el-card>
</template>

<style>
  .el-carousel__item h3 {
    color: black;
    font-size: 15px;
    /*line-height: 300px;*/
    bottom: 43px;
    float: left;
    position: relative;
  }

  .card-carousel {
    margin: 0 auto;
    /*margin-left: -5px;*/
    /*margin-right: 0px;*/
    /*width: 680px;*/
    height: 400px;
  }

  .push {
    margin: 0 auto;
    /*margin-top: -20px;*/
    /*margin-left: -20px;*/
    /*margin-right: -20px;*/
  }

  .el-carousel__item:nth-child(2n) {
    background: whitesmoke;
  }

  .el-carousel__item:nth-child(2n+1) {
    background: white;
  }

  .carousel_img {
    height: 400px;
    /*height: 100%;*/
    width: 100%;
    text-align: center;
  }
  .title {
    color: black;
    font-size: 15px;
    /*line-height: 300px;*/
    float: left;
    position: relative;
  }
</style>

<script>
  export default {
    name: 'Carousel',
    data: function () {
      return {
        items: [{
          id: 1,
          title: 'Picture1',
          img: '../../../static/img/carousel/caro1.jpg',
          link: 'http://www.baidu.com'},
        {
          id: 2,
          title: 'Picture2',
          img: '../../../static/img/carousel/caro2.jpg',
          link: 'https://www.taobao.com/'
        },
        {
          id: 3,
          title: 'Picture3',
          img: '../../../static/img/carousel/caro3.jpg',
          link: 'http://www.'
        },
        {
          id: 4,
          title: 'Picture4',
          img: '../../../static/img/carousel/caro4.jpg',
          link: 'http://'
        }
        ]
      }
    }
  }
</script>
