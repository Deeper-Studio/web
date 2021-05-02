<template>
  <div class="demo-image">
    <div class="block" v-for="fit in fits" :key="fit">
      <span class="demonstration">{{ fit }}</span>
      <el-image
        style="width: 100px; height: 100px"
        :src="url"
        :fit="fit"></el-image>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Authors',
  data () {
    return {
      fits: ['fill'],
      url: 'static/img/Authors/Haris Pervaiz .jpg'
    }
  }
}
// eslint-disable-next-line no-undef
// $('.hover3d').hover3d({
//   selector: '.hover3d-child',
//   invert: true
// })
</script>

<style scoped>
.demo-image__placeholder{
  width: 1000px;
  height: 500px;
}
.block{
  width: 100%;
  height: 100%;
}
</style>
