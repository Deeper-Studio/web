<template>
  <div>
    <el-button type="primary" @click="loadArticles">buttonCont</el-button>
    <el-row style="height: 840px;">
      <search-bar @onSearch="searchResult" ref="searchBar"></search-bar>
<!--      <view-switch class="switch"></view-switch>-->
      <el-tooltip effect="dark" placement="right"
                  v-for="item in books.slice((currentPage-1)*pagesize,currentPage*pagesize)"
                  :key="item.id">
        <p slot="content" style="font-size: 14px;margin-bottom: 6px;">{{item.title}}</p>
        <p slot="content" style="font-size: 13px;margin-bottom: 6px">
          <span>{{item.author}}</span> /
          <span>{{item.date}}</span> /
          <span>{{item.press}}</span>
        </p>
        <p slot="content" style="width: 300px" class="abstract">{{item.abs}}</p>
        <el-card class="box-card" style="width: 900px; background-color: rgb(255, 255, 255); ">
          <el-row>
            <el-col :span="4">
              <div class="cover" style="float: left">
                <el-image src="https://i.loli.net/2019/04/10/5cada7e73d601.jpg" style="margin: auto"></el-image>
                <!--        <img :src="https://i.loli.net/2019/04/10/5cada7e73d601.jpg" alt="封面">-->
              </div>
            </el-col>
            <el-col :span="20">
              <div  class="clearfix" style="position: relative;text-align: left;">
                <span style="font-size: 18px;font-weight: bold"><a href="https://baike.baidu.com/item/%E4%B8%89%E4%BD%93/5739303?fr=aladdin">{{books[0].title}}</a></span>
                <br>
                <span style="font-size: 16px">{{books[0].author}}</span>
                <br>
                <span style="font-size: 16px">{{books[0].press}}</span>
                <br>
                <span style="font-size: 16px; color: rgb(120, 120, 120); font-style: italic">{{books[0].abs}}</span>
              </div>
            </el-col>
          </el-row>
        </el-card>
<!--        版本1-->
<!--        <el-card style="width: 135px;margin-bottom: 20px;height: 233px;float: left;margin-right: 15px" class="book"-->
<!--                 bodyStyle="padding:10px" shadow="hover">-->
<!--          <div class="cover">-->
<!--            <img :src="item.cover" alt="封面">-->
<!--          </div>-->
<!--          <div class="info">-->
<!--            <div class="title">-->
<!--              <a href="">{{item.title}}</a>-->
<!--            </div>-->
<!--          </div>-->
<!--          <div class="author">{{item.author}}</div>-->
<!--        </el-card>-->
      </el-tooltip>
    </el-row>
    <el-row>
      <el-pagination
        @current-change="handleCurrentChange"
        :current-page="currentPage"
        :page-size="pagesize"
        :total="books.length">
      </el-pagination>
    </el-row>
  </div>
</template>

<script>
  import SearchBar from './SearchBar'
  import ViewSwitch from './ViewSwitch'

  export default {
    name: 'Books',
    components: {SearchBar, ViewSwitch},
    data () {
      return {
        books: [
          {
            cover: 'https://i.loli.net/2019/04/10/5cada7e73d601.jpg',
            title: '三体',
            author: '刘慈欣',
            date: '2019-05-05',
            press: '重庆出版社',
            abs: '文化大革命如火如荼进行的同时。军方探寻外星文明的绝秘计划“红岸工程”取得了突破性进展。但在按下发射键的那一刻，历经劫难的叶文洁没有意识到，她彻底改变了人类的命运。地球文明向宇宙发出的第一声啼鸣，以太阳为中心，以光速向宇宙深处飞驰……'
          }
        ],
        // books: [],
        currentPage: 1,
        pagesize: 18
      }
    },
    // mounted: function () {
    //   this.loadBooks()
    // },
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
      loadBooks () {
        var _this = this
        this.$axios.get('/books').then(resp => {
          if (resp && resp.data.code === 200) {
            _this.books = resp.data.result
          }
        })
      },
      handleCurrentChange: function (currentPage) {
        this.currentPage = currentPage
      },
      searchResult () {
        var _this = this
        this.$axios
          .get('/search?keywords=' + this.$refs.searchBar.keywords, {
          }).then(resp => {
          if (resp && resp.data.code === 200) {
            _this.books = resp.data.result
          }
        })
      }
    }
  }
</script>
<style scoped>

  .cover {
    width: 115px;
    height: 172px;
    margin-bottom: 7px;
    overflow: hidden;
    cursor: pointer;
  }

  img {
    width: 115px;
    height: 172px;
    /*margin: 0 auto;*/
  }

  .title {
    font-size: 14px;
    text-align: left;
  }

  .author {
    color: #333;
    width: 102px;
    font-size: 13px;
    margin-bottom: 6px;
    text-align: left;
  }

  .abstract {
    display: block;
    line-height: 17px;
  }

  .el-icon-delete {
    cursor: pointer;
    float: right;
  }

  .switch {
    display: flex;
    position: absolute;
    left: 780px;
    top: 25px;
  }

  a {
    text-decoration: none;
  }

  a:link, a:visited, a:focus {
    color: #3377aa;
  }

</style>
