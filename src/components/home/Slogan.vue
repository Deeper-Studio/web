<template>
  <div>
    <el-card class="box-card">
      <div style="font-size: 45px;color: azure;white-space: nowrap">Stay Hungry. Stay Foolish</div>
      <a href="https://github.com" target="_blank">
        <img src="../../assets/img/icon/icon6.png" alt="" class="git-link">
      </a>
<!--      <a href="https://blog.csdn.net/Neuf_Soleil" target="_blank">-->
<!--        <img src="../../assets/img/icon/csdn.png" alt="" class="csdn-link">-->
<!--      </a>-->
    </el-card>
  </div>
</template>

<script>
  export default {
    name: 'Slogan'
  }
</script>

<style scoped>
  .box-card {
    width: 100%;
    height: 150px;
    background-color: #222;
    text-align: center;
    margin-top: 0px;
  }

  .slogan {
    width: 100%;
  }

  .git-link {
    width: 80px;
    /*position: absolute;*/
  }

  .csdn-link {
    width: 65px;
    /*position: absolute;*/
    margin-bottom: 7px;
    margin-left: 20px;
  }
</style>
