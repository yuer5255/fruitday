<template>
  <el-container>
    <!--头部 开始-->
    <my-header></my-header>
    <!--头部 结束-->
    <!--主体 开始-->
    <el-main>
      <!--轮播图 开始-->
      <el-carousel height="400px" :interval="5000">
        <el-carousel-item v-for="(item,index) in bannerLists" :key="index" name="index" >
          <img :src="item.src">
        </el-carousel-item>
      </el-carousel>
      <!--轮播图 结束-->


      <!--四个小图片 开始-->
      <el-row  style="margin: 20px auto 40px; width: 1280px; text-align: center;">
        <el-col :span="6" v-for="(item,index) in commandLists" :key="index"><div class="grid-content"><img :src="item.src"></div></el-col>
      </el-row>
      <!--四个小图片 结束-->

      <!--楼层 开始-->
      <el-row style="margin: 0 auto;  width: 1290px;">
        <el-row>
          <hr/>
        </el-row>
        <el-row>
          <el-col :span="20"><div class=""><img src="../assets/img/index_floor/title/cards-title.png" alt=""></div></el-col>
          <el-col :span="1" :offset="3"><div class=""><a href="#" style="font-size: 14px; color:#333;">更多 > </a></div></el-col>
        </el-row>
        <!--楼层1 礼品卡券 开始-->
        <el-row :span="24" type="flex" style="flex-flow:row wrap; align-content: flex-start">
          <el-col :span="4.3" v-for="(item,index) in floorLists" :key="index">
            <div class="floor">
              <img :src="item.src"  @click="jumpToDetail(index)">
            </div>
          </el-col>
        </el-row>
        <!--楼层1 礼品卡券 结束-->
      </el-row>
      <!--楼层 结束-->
    </el-main>
    <!--主体 结束-->

    <!--底部 开始-->
    <el-footer>
      <my-footer></my-footer>
    </el-footer>

    <!--底部 结束-->
  </el-container>
</template>

<script>
    export default {
      name: "home",
      //component:{MyHeader,MyFooter},
      data() {
        return {
          bannerLists:[
            {src:require('../assets/img/banner/banner1.jpg')},
            {src:require('../assets/img/banner/banner2.jpg')},
            {src:require('../assets/img/banner/banner3.jpg')},
            {src:require('../assets/img/banner/banner4.jpg')}
          ],
          commandLists:[
            {src:require('../assets/img/command/command1.jpg')},
            {src:require('../assets/img/command/command2.jpg')},
            {src:require('../assets/img/command/command3.jpg')},
            {src:require('../assets/img/command/command4.jpg')},
          ],
          floorLists:[
            {src:require('../assets/img/01-card/1.jpg')},
            {src:require('../assets/img/01-card/2.jpg')},
            {src:require('../assets/img/01-card/3.jpg')},
            {src:require('../assets/img/01-card/4.jpg')},
            {src:require('../assets/img/01-card/5.jpg')},
            {src:require('../assets/img/01-card/6.jpg')},
            {src:require('../assets/img/01-card/7.jpg')},
          ],
        };
      },
      methods: {
        getCarousel(){
          console.log(this.items);
        },
        jumpToDetail(index){
            this.$router.push({path: '/detail/'+index});
        }
      },
      mounted() {
      },
      created(){
      }
    }
</script>

<style scoped>
  .floor{
    width: 248px;
    height: 248px;
    margin: 5px 3px;
    overflow: hidden;
    border-radius: 3px;
    box-shadow: 0 0 5px #ddd;
  }
  .floor img{
    height: 100%;
    width: 100%;
    cursor: pointer;
    overflow: hidden;
  }
  .floor img:hover{
    transform: scale(1.1);
  }
</style>
