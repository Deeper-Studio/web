<template>
  <section class="team ">
    <div class="container">
      <div class="author-title">
        <h1>Featured Authors</h1>
      </div>
      <div class="img">
        <a href='https://www.lancaster.ac.uk/people-profiles/haris-bin-pervaiz' target="_blank" title="Haris Pervaiz">
          <div class="item el-col-md-4">
            <div class="hover3d">
              <div class="hover3d-child">
                <div class="team-img">
                  <img src="static/img/Authors/Haris Pervaiz .jpg" class="img-responsive" alt="">
                </div>
                <div class="info">
                  <div>
                    <h6>Haris Pervaiz</h6>
                    <span>Assistant Professor</span>
                    <p>School of Computing and Communications, Lancaster University, UK</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </a>
      </div>
      <div class="img">
        <a href='https://www.lancaster.ac.uk/sci-tech/about-us/people/damian-arellanes-molina' target="_blank" title="Damian Arellanes">
          <div class="item el-col-md-4">
            <div class="hover3d">
              <div class="hover3d-child">
                <div class="team-img">
                  <img src="static/img/Authors/Damian Arellanes.jpg" class="img-responsive" alt="">
                </div>
                <div class="info">
                  <div>
                    <h6>Damian Arellanes</h6>
                    <span>Assistant Professor</span>
                    <p>School of Computing Science, Lancaster University, UK</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </a>
      </div>
      <div class="img">
        <a href='https://www.lancaster.ac.uk/people-profiles/scott-piao' target="_blank" title="Scott Piao">
          <div class="item el-col-md-4">
            <div class="hover3d">
              <div class="hover3d-child">
                <div class="team-img">
                  <img src="static/img/Authors/Scott Piao.jpg" class="img-responsive" alt="">
                </div>
                <div class="info">
                  <div>
                    <h6>Scott Piao</h6>
                    <span>Assistant Professor</span>
                    <p>School of Computing Science, Lancaster University, UK</p>
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
  name: 'Authors'
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
.author-title{
  position: relative;
  font-size: 32px;
  font-weight: bold;
  font-family: "Times New Roman";
  margin-left: -50%;
}
.img{
  width: 350px;
  height: 350px;
  /*background: black;*/
  display: inline-block;
  margin: 10px;
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
.team .item .info h6 {
  font-size: 16px;
  color: #fff;
  letter-spacing: 1px;
  margin-bottom: 5px;
}
.team .item .info span {
  font-size: 14px;
  font-style: italic;
  /*margin-bottom: 4px;*/
  margin-top: 12px;
  color: #e3e2e2;
}
.team .item .info p {
  margin-bottom: 10px;
  color: #a9a9a9;
}
/*.team .item .info .icon {*/
/*  margin: 0 10px;*/
/*  font-size: 12px;*/
/*  color: #eee;*/
/*  cursor: pointer;*/
/*}*/
/*.pink{*/
/*  color: deeppink;*/
/*  font-weight: bold;*/
/*}*/
</style>
