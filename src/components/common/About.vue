<template>
  <div class="footer">
    <div style="border-top:1px #1F1F1F solid; text-align-all: center ">
<!--      问题1： 字体为何没有居中对齐-->
      <p class="alt" style="color:#999; line-height:0; align:left">&copy; Owned By：Deepers&nbsp;</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Footer'
  }
</script>

<style scoped>

  * {
    margin: 0;
    padding: 0;
    font-family: '微软雅黑', Arial, Helvetica, sans-serif;
  }

  body {
    font-size: 12px;
  }

  div {
    font-size: 12px;
  }

  span {
    font-size: 12px;
  }

  .footer {
    background: #2b2e33;
  }

  .footer .alt {
    overflow: hidden;
    padding: 20px 0;
    width: 1160px;
    margin: auto;
  }

  .footer .alt .foot {
    width: 138px;
    float: left;
  }

  .footer .alt .foot p {
    color: #FFF;
    line-height: 28px;
  }

  a{
    text-decoration: none;
  }

  .footer .alt .foot a {
    color: #999;
    display: block;
    line-height: 24px;
  }
</style>
