<template>
  <body id="searchPic">
<!--  <div style="margin-top: 15px;">-->
<!--    <el-input-->
<!--      @keyup.enter.native="searchClick"-->
<!--      placeholder="Please input"-->
<!--      v-model="keywords"-->
<!--      prefix-icon="el-icon-search"-->
<!--      class="input-with-select">-->
<!--      <el-select v-model="select" slot="prepend" placeholder="请选择">-->
<!--        <el-option label="All" value="1"></el-option>-->
<!--        <el-option label="Books" value="2"></el-option>-->
<!--        <el-option label="Authors" value="3"></el-option>-->
<!--      </el-select>-->
<!--      <el-button slot="append" icon="el-icon-search"></el-button>-->
<!--    </el-input>-->
<!--  </div>-->

    <div class="title_style">
      <p class="template t1">Going Deeper</p>
      <p class="template t2">Going Deeper</p>
    </div>
    <div>
      <el-form>
        <el-form-item class="searchBar">
          <el-input
            @keyup.enter.native="searchClick"
            placeholder="search"
            prefix-icon="el-icon-search"
            size="media"
            style="width: 650px; margin-right: 0px"
            v-model="keywords">
            <el-select v-model="select" slot="prepend" placeholder="Choose">
              <el-option label="All" value="1"></el-option>
              <el-option label="Books" value="2"></el-option>
              <el-option label="Authors" value="3"></el-option>
            </el-select>
            <el-button slot="append" icon="el-icon-search"></el-button>
          </el-input>
          <!--        <el-button size="medium" type="primary" icon="el-icon-search" @click="searchClick">搜索</el-button>-->
        </el-form-item>
      </el-form>
    </div>
  </body>

<!--      </div>-->
<!--    <div class="searchBar">-->
<!--      <el-input-->
<!--        @keyup.enter.native="searchClick"-->
<!--        placeholder="search"-->
<!--        prefix-icon="el-icon-search"-->
<!--        size="media"-->
<!--        style="width: 400px; margin-right: 0px"-->
<!--        v-model="keywords">-->
<!--      </el-input>-->
<!--      <el-button size="medium" type="primary" icon="el-icon-search" @click="searchClick">搜索</el-button>-->
<!--    </div>-->

</template>

<script>
export default {
  name: 'MainSearch',
  data () {
    return {
      keywords: '',
      books: [],
      cardLoading: [],
      input1: '',
      input2: '',
      input3: '',
      select: ''
    }
  },
  methods: {
    searchClick () {
      this.$emit('onSearch')
    }
  }
}
</script>

<style>
  #searchPic {
    background: url('~@/assets/img/bg/searchBar_pic.jpg');
    margin-top: 0px;
    height: 350px;
    width: 100%;
    background-size: cover;
    position: relative;
  }
  body{
    margin: 0px;
  }
  .title_style{
    position: relative;
    width: 100%;
    height: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    padding-top: 120px;
  }
  .template{
    position: absolute;
    font-size: 72px;
    font-weight: bold;
    font-family: "Times New Roman";
  }
  .template.t1{
    margin-left: 4px;
    color: #cb1414;
  }
  .template.t2{
    margin-left: -3px;
    color: #D6E6EE;
    mix-blend-mode: lighten;
  }

  .el-select .el-input {
    width: 130px;
  }
  .input-with-select .el-input-group__prepend {
    background-color: #fff;
  }
  .search_box{
    width: 600px;
    height: 60px;
    background-color: #FFFFFF;
    border-radius: 3px;
    position: absolute;
    left: 50%;
    top: 75px;
    transform: translate(-50%);
  }
  .search_form{
    /*position: absolute;*/
    width: 100%;
    height: 100%;
  }
  .searchBar{
    /*display: flex;*/
    /*width: 300px;*/
    height: 100px;
    justify-content: center;
    align-items: center;

    /*border-radius: 100px;*/
    background-clip: padding-box;
    /*margin: 90px auto;*/
    /*width: 200px;*/
    padding: 60px 100px;
    /*background: #fff;*/
    /*border: 1px solid #eaeaea;*/
    /*box-shadow: 0 0 25px #cac6c6;*/
  }
</style>
