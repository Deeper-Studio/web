<template>
  <div>
<!--    <el-row style="margin: 18px 0px 0px 18px ">-->
<!--      <el-breadcrumb separator-class="el-icon-arrow-right">-->
<!--        <el-breadcrumb-item :to="{ path: '/admin/dashboard' }">管理中心</el-breadcrumb-item>-->
<!--        <el-breadcrumb-item>内容管理</el-breadcrumb-item>-->
<!--        <el-breadcrumb-item>文章管理</el-breadcrumb-item>-->
<!--      </el-breadcrumb>-->
<!--    </el-row>-->
<!--    <el-link href="/admin/content/editor" :underline="false" target="_blank" class="add-link">-->
<!--      <el-button type="success">写文章</el-button>-->
<!--    </el-link>-->
    <el-button type="primary" @click="loadArticles">buttonCont</el-button>
<!--    <el-card style="margin: 18px 2%;width: 95%">-->
<!--      <el-table-->
<!--        :data="articles"-->
<!--        stripe-->
<!--        style="width: 100%"-->
<!--        :max-height="tableHeight">-->
<!--        <el-table-column-->
<!--          type="selection"-->
<!--          width="55">-->
<!--        </el-table-column>-->
<!--        <el-table-column type="expand">-->
<!--          <template slot-scope="props">-->
<!--            <el-form label-position="left" inline>-->
<!--              <el-form-item>-->
<!--                <span>{{ props.row.articleAbstract }}</span>-->
<!--              </el-form-item>-->
<!--            </el-form>-->
<!--          </template>-->
<!--        </el-table-column>-->
<!--        <el-table-column-->
<!--          prop="articleTitle"-->
<!--          label="Title(展开查看摘要）"-->
<!--          fit>-->
<!--          三体-->
<!--        </el-table-column>-->
<!--        <el-table-column-->
<!--          prop="articleDate"-->
<!--          label="Date"-->
<!--          width="200">-->
<!--          2020.12.03-->
<!--        </el-table-column>-->
<!--        <el-table-column-->
<!--          fixed="right"-->
<!--          label="Operation"-->
<!--          width="180">-->
<!--          <template slot-scope="scope">-->
<!--            <el-button-->
<!--              @click.native.prevent="viewArticle(scope.row.id)"-->
<!--              type="text"-->
<!--              size="small">-->
<!--              查看-->
<!--            </el-button>-->
<!--            <el-button-->
<!--              @click.native.prevent="acceptArticle(scope.row)"-->
<!--              type="text"-->
<!--              size="small"-->
<!--              style="color: green">-->
<!--              通过-->
<!--            </el-button>-->
<!--            <el-button-->
<!--              @click.native.prevent="refuseArticle(scope.row.id)"-->
<!--              type="text"-->
<!--              size="small" style="color: #b31d28">-->
<!--              拒绝-->
<!--            </el-button>-->
<!--          </template>-->
<!--        </el-table-column>-->
<!--      </el-table>-->
<!--      <div style="margin: 20px 0 50px 0">-->
<!--        <el-pagination-->
<!--          background-->
<!--          style="float:right;"-->
<!--          layout="total, prev, pager, next, jumper"-->
<!--          @current-change="handleCurrentChange"-->
<!--          :page-size="pageSize"-->
<!--          :total="total">-->
<!--        </el-pagination>-->
<!--      </div>-->
<!--    </el-card>-->
  </div>
</template>

<script>
export default {
  name: 'Review',
  data () {
    return {
      articles: [
        {

        }
      ],
      pageSize: 10,
      total: 0
    }
  },
  mounted () {
    this.loadArticles()
  },
  computed: {
    tableHeight () {
      return window.innerHeight - 320
    }
  },
  methods: {
    loadArticles () {
      // var _this = this
      this.$axios('/paper/all').then(resp => {
        console.log(resp)
      })
      // this.$axios.get('/article/' + this.pageSize + '/1').then(resp => {
      //   if (resp && resp.data.code === 200) {
      //     _this.articles = resp.data.result.content
      //     _this.total = resp.data.result.totalElements
      //   }
      // })
    },
    handleCurrentChange (page) {
      var _this = this
      this.$axios.get('/article/' + this.pageSize + '/' + page).then(resp => {
        if (resp && resp.data.code === 200) {
          _this.articles = resp.data.result.content
          _this.total = resp.data.result.totalElements
        }
      })
    },
    viewArticle (id) {
      let articleUrl = this.$router.resolve(
        {
          path: '../../jotter/article',
          query: {
            id: id
          }
        }
      )
      window.open(articleUrl.href, '_blank')
    },
    // editArticle (article) {
    //   this.$router.push(
    //     {
    //       name: 'Editor',
    //       params: {
    //         article: article
    //       }
    //     }
    //   )
    // },
    acceptArticle (id) {
      this.$confirm('此论文符合要求, 是否接受?', '提示', {
        confirmButtonText: '确定',
        cancelButtonText: '取消',
        type: 'warning'
      }).then(() => {
          this.$axios
            .post('/admin/article' + id, 1).then(resp => {
            if (resp && resp.data.code === 200) {
              this.loadArticles()
            }
          })
        }
      ).catch(() => {
        this.$message({
          type: 'info',
          message: '已取消操作'
        })
      })
    },
    refuseArticle (id) {
      this.$confirm('此论文不达标, 是否驳回?', '提示', {
        confirmButtonText: '确定',
        cancelButtonText: '取消',
        type: 'warning'
      }).then(() => {
          this.$axios
            .post('/admin/article' + id, 0).then(resp => {
            if (resp && resp.data.code === 200) {
              this.loadArticles()
            }
          })
        }
      ).catch(() => {
        this.$message({
          type: 'info',
          message: '已取消操作'
        })
      })
    }
  }
}
</script>

<style scoped>
.add-link {
  margin: 18px 0 15px 10px;
  float: left;
}
</style>
