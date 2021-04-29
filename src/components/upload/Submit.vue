<template>
  <div style="margin-top: 20px">
    <div class="articles-area">
<!--      标题栏-->
      <el-card style="background-color: rgb(248,248,248);">
        <span style="position: absolute;width: 1160px; right: 190px; top: 90px; font-size: 18px;font-weight: bold">Paper Submission</span>
      </el-card>
<!--      文章信息-->
      <el-card style="text-align: left;">
        <div style="margin: 20px;position: relative;width: 950px; left:35px;">
          <span style="font-size: 16px;font-weight: bold">论文信息</span>
          <hr color="green" width="200px" align="left">
        </div>
        <div class="paper-submit">
          <el-form :label-position="labelPosition" label-width="80px" :model="paper">
            <el-form-item label="Title">
              <el-input v-model="paper.title"></el-input>
            </el-form-item>
            <el-form-item label="Keywords">
              <el-input v-model="paper.keywords"></el-input>
            </el-form-item>
            <el-form-item label="Abstract">
              <el-input type="textarea" v-model="paper.abstract"></el-input>
            </el-form-item>
          </el-form>
          <div class="upload">
            <!--              问题4-->
<!--            和表单一起实现上传（这种情况一般都是文件上传之后，后端返回保存在服务器的文件名，最后和我们的表单一起上传）-->
            <el-upload
              accept=".pdf, .PDF"
              drag
              action="http://localhost:8090/paper/pdf"
              :auto-upload="false"
            >
              <i class="el-icon-upload"></i>
              <div class="el-upload__text">只能上传pdf文件,将文件拖到此处，或<em>点击上传</em></div>
            </el-upload>
          </div>
        </div>
      </el-card>
<!--      作者信息-->
      <el-card style="text-align: left; position: relative; top: 10px; height: 400px">
        <div style="margin: 20px;position: relative;width: 850px; left:35px;">
          <span style="font-size: 16px;font-weight: bold">作者信息</span>
          <hr color="green" width="200px" align="left">
        </div>
        <div class="paper-submit">
          <el-form :label-position="labelPosition" label-width="80px" :model="author">
            <el-form-item label="Name">
              <el-input v-model="author.name"></el-input>
            </el-form-item>
            <el-form-item label="Campus">
              <el-input v-model="author.campus"></el-input>
            </el-form-item>
            <el-form-item label="E-mail">
              <el-input v-model="author.e_mail"></el-input>
            </el-form-item>
          </el-form>
        </div>
        <div style="position:relative; top: 25px;right: -380px">
          <el-button type="primary" style="width: 160px" @click="paper_submit">buttonCont</el-button>
          <el-button type="success" style="width: 160px">buttonCont</el-button>
        </div>
      </el-card>
      <about id="about" style="position:relative; top: 2px "></about>
    </div>
  </div>
</template>

<script>
import About from '../common/About'

export default {
  name: 'Submit',
  components: {About},
  data () {
    return {
      articles: [],
      pageSize: 4,
      total: 0,
      labelPosition: 'left',
      paper: {
        title: '',
        keywords: '',
        abstract: ''
      },
      author: {
        name: '',
        campus: '',
        e_mail: ''
      }
    }
  },
  // // mounted () {
  // //   this.loadArticles()
  // },
  methods: {
    // httpRequest (param) {
    //   this.file.push(param.file)
    //   },
    paper_submit () {
      console.log(this.paper)
      var _this = this
      this.$axios
        .post('/submit', {
          title: this.paper.title,
          keywords: this.paper.keywords,
          abstract: this.paper.abstract,
          author: this.author.name,
          campus: this.author.campus,
          email: this.author.e_mail
        })
        .then(resp => {
          if (resp.data.code === 200) {
            console.log(resp.data.code)
          } else {
            this.$alert(resp.data.message, '提示', {
              confirmButtonText: '确定'
            })
          }
        })
        .catch(failResponse => {
          console.log('Fail to connect the serve')
          // 测试
          var path = _this.$route.query.redirect
          console.log(path)
          _this.$router.replace({path: '/submit/success'})
        })
    }
  }
}
</script>

<style scoped>
.articles-area {
  width: 1160px;
  height: 750px;
  margin-left: auto;
  margin-right: auto;
}

.paper-submit{
  position: relative;
  /*top: 50px;*/
  width: 950px;
  margin: auto;
}
.upload{
  width: 100px;
  position: relative;
  left: 80px;
}
/*.el-upload-dragger {*/
/*  background-color: #fff;*/
/*  border: 1px dashed #d9d9d9;*/
/*  border-radius: 6px;*/
/*  -webkit-box-sizing: border-box;*/
/*  box-sizing: border-box;*/
/*  width: 110px;*/
/*  height: 140px;*/
/*  text-align: center;*/
/*  position: relative;*/
/*  overflow: hidden;*/
/*}*/
.article-link {
  text-decoration: none;
  color: #606266;
}

.article-link:hover {
  color: #409EFF;
}

.horizontal{
  float:left;
  position: relative;
  margin-left: 80px;
  width: 400px;
}
</style>
