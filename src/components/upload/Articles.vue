<template>
  <div style="margin-top: 40px">
    <!--<el-button @click="addArticle()">添加文章</el-button>-->
    <div class="articles-area">
      <el-card style="text-align: left">
        <div v-for="article in articles" :key="article.id">
          <div style="float:left;width:85%;height: 150px;">
            shipfhpiew
<!--            <el-row :gutter="2">-->
<!--              <el-col :span="3"><div class="grid-content bg-purple-light"></div></el-col>-->
<!--              <el-col :span="18"><div class="grid-content bg-white">-->
<!--                <el-row :gutter="2">-->
<!--                  <el-col :span="20" offset="2"><div class="grid-content bg-white">-->
<!--                    <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm" label-position="left">-->
<!--                      <el-form-item label="Title" prop="title">-->
<!--                        <el-input v-model="ruleForm.title"></el-input>-->
<!--                      </el-form-item>-->
<!--                      <el-form-item label="Keywords" prop="keyword">-->
<!--                        <el-input v-model="ruleForm.keyword"></el-input>-->
<!--                      </el-form-item>-->
<!--                      <el-form-item label="Abstract" prop="abstract">-->
<!--                        <el-input type="textarea" v-model="ruleForm.abstract"></el-input>-->
<!--                      </el-form-item>-->
<!--                      <el-form-item label=" Add File ">-->
<!--                        <el-upload-->
<!--                          class="upload-demo"-->
<!--                          drag-->
<!--                          action="http://localhost:8088/"-->
<!--                          multiple="false"-->
<!--                          accept=".pdf, .PDF"-->
<!--                          :http-request="requestFile"-->
<!--                          :auto-upload="false"-->
<!--                          :on-change="handlePreview"-->
<!--                          file-list="filelist"-->

<!--                        >-->
<!--                          <i class="el-icon-upload"></i>-->
<!--                          <div class="el-upload__text">将文件拖到此处，或<em>点击上传</em></div>-->
<!--                          <div class="el-upload__tip" slot="tip">只能上传jpg/png文件，且不超过500kb</div>-->
<!--                        </el-upload>-->
<!--                      </el-form-item>-->
<!--                      <el-row :gutter="2">-->
<!--                        <el-col :span="11">-->
<!--                          <el-form-item label="Name" prop="name" required>-->
<!--                            <el-input clearable v-model="ruleForm.name" placeholder="placeholder"></el-input>-->
<!--                          </el-form-item>-->
<!--                        </el-col>-->
<!--                        <el-col :span="2">  </el-col>-->
<!--                        <el-col :span="11">-->
<!--                          <el-form-item clearable label="School" prop="school" required="">-->
<!--                            <el-input v-model="ruleForm.school" placeholder="placeholder"></el-input>-->
<!--                          </el-form-item>-->
<!--                        </el-col>-->
<!--                      </el-row>-->
<!--                      <el-row :gutter="2">-->
<!--                        <el-col :span="11">-->
<!--                          <el-form-item clearable label="Email" prop="email" required>-->
<!--                            <el-input v-model="ruleForm.email" placeholder="placeholder"></el-input>-->
<!--                          </el-form-item>-->
<!--                        </el-col>-->
<!--                        <el-col :span="2">  </el-col>-->
<!--                        <el-col :span="11">-->
<!--                          <el-form-item clearable label="Address" prop="address" required="">-->
<!--                            <el-input v-model="ruleForm.address" placeholder="placeholder"></el-input>-->
<!--                          </el-form-item>-->
<!--                        </el-col>-->
<!--                      </el-row>-->

<!--                      <el-form-item>-->
<!--                        <el-button type="primary" @click="submitForm('ruleForm')">Create</el-button>-->
<!--                        <el-button @click="resetForm('ruleForm')">Reset</el-button>-->
<!--                      </el-form-item>-->
<!--                    </el-form>-->
<!--                  </div></el-col>-->
<!--                </el-row>-->
<!--              </div></el-col>-->
<!--              <el-col :span="3"><div class="grid-content bg-purple-light"></div></el-col>-->
<!--            </el-row>-->
<!--            <router-link class="article-link" :to="{path:'jotter/article',query:{id: article.id}}"><span style="font-size: 20px"><strong>{{article.articleTitle}}</strong></span></router-link>-->
<!--            <el-divider content-position="left">{{article.articleDate}}</el-divider>-->
<!--            <router-link class="article-link" :to="{path:'jotter/article',query:{id: article.id}}"><p>{{article.articleAbstract}}</p></router-link>-->
          </div>
          <el-image
            style="margin:18px 0 0 30px;width:100px;height: 100px"
            :src="article.articleCover"
            fit="cover"></el-image>
          <el-divider></el-divider>
        </div>
      </el-card>
    </div>
    <el-pagination
      background
      layout="total, prev, pager, next, jumper"
      @current-change="handleCurrentChange"
      :page-size="pageSize"
      :total="total">
    </el-pagination>
  </div>
</template>

<script>

  export default {
    name: 'Articles',
    data () {
      return {
        articles: [],
        pageSize: 4,
        total: 0
      }
    },
    mounted () {
      this.loadArticles()
    },
    methods: {
      loadArticles () {
        var _this = this
        this.$axios.get('/article/' + this.pageSize + '/1').then(resp => {
          if (resp && resp.data.code === 200) {
            _this.articles = resp.data.result.content
            _this.total = resp.data.result.totalElements
          }
        })
      },
      handleCurrentChange (page) {
        var _this = this
        this.$axios.get('/article/' + this.pageSize + '/' + page).then(resp => {
          if (resp && resp.data.code === 200) {
            _this.articles = resp.data.result.content
            _this.total = resp.data.result.totalElements
          }
        })
      }
    }
  }
</script>

<style scoped>
  .articles-area {
    width: 990px;
    height: 750px;
    margin-left: auto;
    margin-right: auto;
  }

  .article-link {
    text-decoration: none;
    color: #606266;
  }

  .article-link:hover {
    color: #409EFF;
  }
</style>
