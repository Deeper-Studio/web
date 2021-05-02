<template>
  <section class="team ">
    <div class="container">
      <div class="article-title">
        <h1>Featured Articles</h1>
      </div>
      <div class="img">
        <a href='https://www.sciencedirect.com/science/article/abs/pii/S0167739X19320291' target="_blank" title="Evaluating IoT service composition mechanisms for the scalability of IoT systems">
          <div class="item el-col-md-4">
            <div class="hover3d">
              <div class="hover3d-child">
                <div class="team-img">
                  <img src="static/img/FeaturedArticles/IoT1.jpg" class="img-responsive" alt="">
                </div>
                <div class="info">
                  <div>
                    <h5>Evaluating IoT service composition mechanisms for the scalability of IoT systems</h5>
                    <h6>Damian Arellanes</h6>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </a>
      </div>
      <div class="img">
        <a href='https://ieeexplore.ieee.org/abstract/document/8831195' target="_blank" title="Workflow Variability for Autonomic IoT Systems">
          <div class="item el-col-md-4">
            <div class="hover3d">
              <div class="hover3d-child">
                <div class="team-img">
                  <img src="static/img/FeaturedArticles/IoT2.jpg" class="img-responsive" alt="">
                </div>
                <div class="info">
                  <div>
                    <h5>Workflow Variability for Autonomic IoT Systems</h5>
                    <h6>Damian Arellanes</h6>
<!--                    <span>Assistant Professor</span>-->
<!--                    <p>School of Computing Science, Lancaster University, UK</p>-->
                  </div>
                </div>
              </div>
            </div>
          </div>
        </a>
      </div>
      <div class="img">
        <a href='https://ieeexplore.ieee.org/document/8767238' target="_blank" title="Decentralized Data Flows in Algebraic Service Compositions for the Scalability of IoT Systems">
          <div class="item el-col-md-4">
            <div class="hover3d">
              <div class="hover3d-child">
                <div class="team-img">
                  <img src="static/img/FeaturedArticles/IoT3.jpg" class="img-responsive" alt="">
                </div>
                <div class="info">
                  <div>
                    <h5>Decentralized Data Flows in Algebraic Service Compositions for the Scalability of IoT Systems</h5>
                    <h6>Damian Arellanes</h6>
<!--                    <span>Assistant Professor</span>-->
<!--                    <p>School of Computing Science, Lancaster University, UK</p>-->
                  </div>
                </div>
              </div>
            </div>
          </div>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'FeaturedArticles'
}
</script>

<style scoped>
body{
  margin: 0;
  padding: 0;
  /*background: #333333;*/
}
.container{
  /*text-align: center;*/
  margin-top: 60px;
}
.article-title{
  position: relative;
  font-size: 32px;
  font-weight: bold;
  font-family: "Times New Roman";
  margin-left: -50%;
}
.img{
  width: 375px;
  height: 275px;
  /*background: black;*/
  display: inline-block;
  margin: 7px;
  margin-top: -10px;
  /*background-size: cover;*/
  /*background-repeat: no-repeat;*/
}
body{
  font-family: 'Roboto Condensed', sans-serif;

}
.team .item {
  text-align: center;
  position: relative;
  width: 100%;
  height: 100%;
  /*margin-bottom: 15px;*/
  overflow: hidden;
}
.team .item:hover .info {
  bottom: 50px;
}
.team .item:hover .team-img:after {
  opacity: 1;
  visibility: visible;
}
.team .item .team-img {
  overflow: hidden;
  /*border-radius: 4px;*/
  position: relative;
}
.team .item .team-img:after {
  content: '';
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.8);
  background: linear-gradient(to top, #111, rgba(0, 0, 0, 0.4));
  opacity: 0;
  visibility: hidden;
  -webkit-transition: all .4s;
  transition: all .4s;
}
.team .item .info {
  position: absolute;
  bottom: -500px;
  left: 0;
  padding: 0 15px;
  width: 100%;
  z-index: 4;
  -webkit-transition: all .4s;
  transition: all .4s;
}
.team .item .info h5 {
  font-size: 16px;
  font-weight: bold;
  color: #fff;
  letter-spacing: 1px;
  margin-bottom: -35px;
  margin-right: 10px;
  padding-bottom: 8px;
  text-align: left;
  /*color: #a9a9a9;*/
}
.team .item .info h6 {
  font-size: 14px;
  font-style: italic;
  font-weight: normal;
  color: #fff;
  letter-spacing: 1px;
  margin-bottom: -35px;
  margin-right: 10px;
  text-align: left;
  /*color: #a9a9a9;*/
}
.team .item .info span {
  font-size: 14px;
  font-style: italic;
  /*margin-bottom: -30%;*/
  margin-top: 200px;
  /*padding-bottom: 0px;*/
  text-align: left;
  /*margin-left: -70%;*/
  color: #e3e2e2;
}
.team .item .info p {
  margin-bottom: 10px;
  color: #a9a9a9;
}
</style>
