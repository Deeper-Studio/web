<template>
  <el-carousel :interval="4000" type="card" height="200px">asfsfsfwe
    <el-carousel-item v-for="item in imgs" :key="item">
      <div>
        <el-image style :src="item.idView" fit="fill"></el-image>
        <h3 class="h3_title">{{item.title}}</h3>
      </div>
    </el-carousel-item>
  </el-carousel>
</template>

<script>
export default {
  name: 'MyCarousel',
  data () {
    return {
      imgs: [
        {id: 0, idView: require('../../assets/img/carousel/caro1.jpg')},
        {id: 1, idView: require('../../assets/img/carousel/caro2.jpg')},
        {id: 2, idView: require('../../assets/img/carousel/caro3.jpg')},
        {id: 3, idView: require('../../assets/img/carousel/caro4.jpg')}]
    }
  }
}
</script>

<style scoped>
.el-carousel__item h3 {
  color: #fff;
  font-size: 14px;
  opacity: 0.75;
  line-height: 200px;
  margin:10px;
}

.el-carousel__item:nth-child(2n) {
  background-color: #fff;
}

.el-carousel__item:nth-child(2n+1) {
  background-color: #fff;
}

.h3_title{
  position: absolute;
  left: 10px;
  bottom: 20px;
}
</style>
