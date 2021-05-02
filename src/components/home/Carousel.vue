<template>
<!--  <el-card class="card-carousel">-->
  <el-carousel  class="push" :interval="4000" arrow="always">
<!--    <el-carousel-item v-for="item in items" :key="item.id">-->
    <el-carousel-item v-for="item in items" :key="item.id">
      <a :href=item.link target="_blank">
        <img :src=item.img alt="" class="carousel_img">
        <span class="newsTitle">{{item.content}}</span>
      </a>
<!--      <a :href=item.link target="_blank">-->
<!--        <img :src=item.img alt="" class="carousel_img">-->
<!--        <span class="ms">Surge in iPhone sales sees Apple's profits double</span>-->
<!--      </a>-->
<!--        <div class="info">-->
<!--          <div>-->
<!--            &lt;!&ndash;          <h6>Haris Pervaiz</h6>&ndash;&gt;-->
<!--            &lt;!&ndash;          <span>Assistant Professor</span>&ndash;&gt;-->
<!--            <p>School of Computing and Communications, Lancaster University, UK</p>-->
<!--          </div>-->
<!--        </div>-->
<!--      问题2： 标题加不上-->
<!--      <el-card class="title">-->
<!--        <h3>{{item.title}}</h3>-->
<!--      </el-card>-->
    </el-carousel-item>
  </el-carousel>
<!--  </el-card>-->
</template>

<script>
export default {
  name: 'Carousel',
  data: function () {
    return {
      items: [{
        id: 1,
        title: 'Surge in iPhone sales sees Apple\'s profits double',
        img: 'static/img/carousel/news1.jpg',
        content: 'Surge in iPhone sales sees Apple\'s profits double',
        link: 'https://www.bbc.com/news/business-56920146'},
        {
          id: 2,
          title: 'App used by emergency services under scrutiny',
          img: 'static/img/carousel/news2.jpg',
          link: 'https://www.bbc.com/news/technology-56901363',
          content: 'App used by emergency services under scrutiny'
        },
        {
          id: 3,
          title: 'Nature \'more important than ever during lockdown\'',
          img: 'static/img/carousel/news3.jpg',
          link: 'https://www.bbc.com/news/science-environment-56889322',
          content: 'Nature \'more important than ever during lockdown\''
        },
        {
          id: 4,
          title: 'Mars Ingenuity helicopter mission extended by Nasa',
          img: 'static/img/carousel/news4.jpg',
          link: 'https://www.bbc.com/news/science-environment-56951752',
          content: 'Mars Ingenuity helicopter mission extended by Nasa'
        }
      ]
    }
  }
}
</script>

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
    /*margin: 0 auto;*/
    /*margin-left: -5px;*/
    /*margin-right: 0px;*/
    width: 100%;
    height: 100%;
  }
.item.content{
  font-size: 16px;
  color: #fff;
  letter-spacing: 1px;
  margin-bottom: 5px;
}
  .push {
    width: 1050px;
    height: 100%;
    margin-left: auto;
    margin-right: auto;
    margin-top: 20px;
    /*margin: 0 auto;*/
    /*margin-top: -20px;*/
    /*margin-left: -20px;*/
    /*margin-right: -20px;*/
  }
  .push .info {
    color: black;
    /*position: absolute;*/
    bottom: 0px;
    left: 0;
    padding: 0 15px;
    width: 100%;
    /*z-index: 4;*/
    /*-webkit-transition: all .4s;*/
    /*transition: all .4s;*/
  }
  .el-carousel__item:nth-child(2n) {
    background: whitesmoke;
  }

  .el-carousel__item:nth-child(2n+1) {
    background: white;
  }

  .carousel_img {
    /*height: 400px;*/
    height: 100%;
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
  .newsTitle { /*绝对位置*/
    position: absolute;
    /*background: #ffffff; !*透明度*!*/
    opacity: 0.8; /*span标签的大小*/
    width: 100%;
    height: 80px; /*偏移到div上*/
    left: 0; /*span标签下移*/
    bottom: 0.1px;
    text-align: center;
    color: #ffffff;
    font-size: 36px;
    /*font-family: "Times New Roman";*/
    letter-spacing: 1px;
    font-weight: bold;
    text-align: left;
    margin-bottom: -15px;
    margin-left: 10px;
  }
   </style>
