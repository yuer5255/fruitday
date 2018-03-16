<template>
  <el-container>
    <my-header></my-header>
    <el-main>
      <!--面包屑导航 开始-->
      <el-breadcrumb separator-class="el-icon-arrow-right">
        <el-breadcrumb-item :to="{ path: '/' }"><span class="a_green">首页</span></el-breadcrumb-item>
        <el-breadcrumb-item><span class="a_green">新鲜水果</span></el-breadcrumb-item>
        <el-breadcrumb-item>佳沛意大利绿奇异果（原箱）</el-breadcrumb-item>
      </el-breadcrumb>
      <!--面包屑导航 结束-->

      <!--图片与详情 开始-->
      <el-row style="margin-top: 20px;">
        <el-col :span="12" style="width: 700px; height: 560px;" >
          <!--左侧图片-->
          <div >
            <el-row>
              <!--竖排小图-->
              <el-col :span="6" class="detail-small-pic">
                <div v-for="(item,index) of picList" @click="changeSelected(index)" :class="{cur:index==tmpIndex}"><img :src="require('../assets/'+item.src)"></div>
              </el-col>
              <!--大图-->
              <el-col :span="18" class="detail-big-pic">
                <div v-for="(item,index) of picList" ><img :src="require('../assets/'+item.src)" :class="{cur:index==tmpIndex}"></div>
              </el-col>
            </el-row>
        </div>
        </el-col>
        <!--右侧详情-->
        <el-col :span="12" style="margin-left:20px; width: 550px; height: 560px; padding-left:20px;" class="">
          <div style="border-bottom: 1px solid #ddd;">
            <!--标题-->
            <el-row>
              <el-col><h3>佳沛意大利绿奇异果（原箱）</h3></el-col>
            </el-row>
            <!--一句简介-->
            <el-row>
              <el-col><p class="title_describeapp">细嫩绿芯 酸甜爽口</p></el-col>
            </el-row>
            <!--价格-->
            <el-row class="good-details-price">
              <el-col :span="4"><span class="gray">果园价</span></el-col>
              <el-col :span="4"><span class="green_price">￥199.00</span></el-col>
              <el-col :span="4" :offset="12" ><img class="erweima" src="../assets/img/03-product-detail/erweima/erweima_lg.png"></el-col>
            </el-row>
            <!--规格-->
            <el-row>
              <el-col :span="4"><span class="gray">规格</span></el-col>
              <el-col :span="4"><el-button type="success" size="mini">36个</el-button></el-col>
            </el-row>
            <!--配送地址-->
            <el-row>
              <el-col :span="4"><span class="gray">配送至</span></el-col>
              <el-col :span="4">
                <el-dropdown>
                  <el-button type="primary" size="mini">
                    上海<i class="el-icon-arrow-down el-icon--right"></i>
                  </el-button>
                  <el-dropdown-menu slot="dropdown">
                    <el-dropdown-item>黄金糕</el-dropdown-item>
                    <el-dropdown-item>狮子头</el-dropdown-item>
                    <el-dropdown-item>螺蛳粉</el-dropdown-item>
                    <el-dropdown-item>双皮奶</el-dropdown-item>
                    <el-dropdown-item>蚵仔煎</el-dropdown-item>
                  </el-dropdown-menu>
                </el-dropdown>
              </el-col>
              <el-col :span="4"><span class="a_green">有货</span></el-col>
            </el-row>
            <!--购买数量-->
            <el-row>
              <el-col :span="4"><span class="gray">数量</span></el-col>
              <el-col :span="4">
                <div class="price_modify">
                  <span class="price_reduce" @click="cartNum">-</span>
                  <input type="text" :value="countNum">
                  <span class="price_add" @click="cartNum">+</span>
                </div>
              </el-col>
            </el-row>
            <!--立即购买与加入购物车-->
            <el-row>
              <el-col :span="4" :offset="4"><el-button type="success" plain>立即购买</el-button></el-col>
              <el-col :span="4" :offset="2"><el-button type="success">加入购物车</el-button></el-col>
            </el-row>
          </div>

          <!--储藏方法 开始-->
          <div style="margin-top:10px;">
            <el-row>
              <el-col :span="12">
                <el-row>
                  <el-col :span="8" class="gray">储藏方法</el-col>
                  <el-col :span="8">0° 冷藏</el-col>
                </el-row>
              </el-col>
              <el-col :span="12">
                <el-row>
                  <el-col :span="8" class="gray">商品编号</el-col>
                  <el-col :span="8">20149333</el-col>
                </el-row>
              </el-col>
            </el-row>
          </div>
          <!--储藏方法 结束-->
        </el-col>
      </el-row>
      <!--图片与详情 结束-->

      <!--简介与最近浏览 开始-->
      <el-row class="good-details-preview">
        <el-col :span="18"  class="good-details grid-content bg-purple">
          <el-row>
            <el-col :span="4" class="lightColor">商品简介</el-col>
            <el-col :span="4">顾客评论（254）</el-col>
            <el-col :span="4" :offset="12">加入购物车</el-col>
          </el-row>
          <!--产地 开始-->
          <el-row>
            <el-col :span="3">产地</el-col>
            <el-col :span="21" style="text-align: left; padding-left: 10px;">意大利</el-col>
          </el-row>
          <!--产地 结束-->

          <!--储藏方法 开始-->
          <el-row>
            <el-col :span="3">储藏方法</el-col>
            <el-col :span="21" style="text-align: left; padding-left: 10px;">0°及以上冷藏</el-col>
          </el-row>
          <!--储藏方法 结束-->

          <!--单重 开始-->
          <el-row>
            <el-col :span="3">单重</el-col>
            <el-col :span="21" style="text-align: left; padding-left: 10px;">80-95g</el-col>
          </el-row>
          <!--单重 结束-->

          <!--长图开始-->
          <div class="longPic">
            <div v-for="(item,index) of longPicLists">
              <img :src="require('../assets/'+item.src)">
            </div>
          </div>
          <!--长图结束-->
        </el-col>
        <el-col :span="5" :offset="1" class="grid-content bg-purple-light">
          <el-row>
            <el-col>最近浏览过</el-col>
          </el-row>
        </el-col>
      </el-row>
      <!--简介与最近浏览 结束-->
    </el-main>
    <el-footer>
      <my-footer></my-footer>
    </el-footer>
  </el-container>
</template>

<script>
    export default {
        name: "detail",
        data() {
          return{
            proId:null,
            picList:[],
            longPicLists:[],
            tmpIndex:0,
            countNum:1,
            cur:false,//是否添加样式
          }
        },
        methods: {
          getCarouselPics(){//获取小图
            this.picList.push(
              {src:'img/03-product-detail/md/1-1.jpg'},
              {src:'img/03-product-detail/md/1-2.jpg'},
              {src:'img/03-product-detail/md/1-3.jpg'},
              {src:'img/03-product-detail/md/1-4.jpg'}
            );
          },
          changeSelected(index){//点击图片切换样式
            this.tmpIndex = index;
          },
          cartNum(event){//对商品数量做修改
            this.proId = this.$route.params.id;//商品id
            if(event.target.className=='price_add'){//数量加
                this.countNum ++;
            }else if(event.target.className=='price_reduce'){//数量减
                this.countNum>=2 ? this.countNum -- : 1;
            }
          },
          getLongPicLists(){//获取长图
            this.longPicLists.push(
              {src:'img/03-product-detail/product-details/1-1.jpg'},
              {src:'img/03-product-detail/product-details/1-2.jpg'},
              {src:'img/03-product-detail/product-details/1-3.jpg'},
              {src:'img/03-product-detail/product-details/1-4.jpg'}
            );
            console.log(this.longPicLists);
          }
        },
        beforeMount() {
          this.getCarouselPics();
          this.getLongPicLists();
        }
        // watch: {
        //   '$route' (to, from) {
        //     // 对路由变化作出响应...
        //   }
        // }
    }
</script>

<style scoped>
  .el-header{
    box-shadow: 0 2px 8px rgba(230,230,230,0.75);
    border-bottom: 1px solid #f1f1f1;
  }

  .el-main{
    width: 1290px;
    margin: 40px auto;
  }

  /*小图片*/
  .detail-small-pic{
    width: 140px;
    height: 560px;
  }
  .detail-small-pic>div{
    width: 136px;
    height:136px;
    margin-bottom: 2px;
    border: 1px solid transparent;
  }

  .detail-small-pic img,.detail-big-pic img{
    width: 100%;
    height: 100%;
  }

  .detail-small-pic .cur{
    border: 1px solid #f6af0d;
  }

  /*大图片*/
  .detail-big-pic{
    width: 560px;
    height:560px;
    overflow: hidden;
    position: relative;
  }
  .detail-big-pic img{
    position: absolute;
    left:0;
    top:0;
    z-index:1;
  }
  .detail-big-pic img.cur{
    z-index:10;
  }

  /*购买商品须知 开始*/
  .erweima{
    width: 30px;
    height: 30px;
    vertical-align: middle;
  }

  .title_describeapp{
    height: 48px;
    font-size: 16px;
    line-height: 48px;
    color: #999;
  }

  /*商品价格*/
  .good-details-price{
    width: 552px;
    height: 75px;
    line-height: 75px;
    padding-left: 10px;
    background: url('../assets/img/icons.png') no-repeat 0 -48px
  }

  .price_modify>span:hover{
    cursor: pointer;
  }
  /*购买商品须知 结束*/

  /*商品详情与最近预览*/
  .good-details-preview>.el-col:first-child{
    border-bottom: 1px solid #d8d8d8;
  }

  .good-details{
    color: #000;
  }

  .good-details>.el-row{
    margin:0;
    border-top: 1px solid #d8d8d8;
    border-left: 1px solid #d8d8d8;
    text-align: center;
  }

  .good-details .el-col{
    height: 39px;
    line-height:39px;
    border-right: 1px solid #d8d8d8;
  }

  .green_price{
    color: #64a131;
    font-size: 24px;
    font-weight: 900;
  }

  .price_modify{
    display: flex;
    width: 93px;
    height:24px;
    justify-content: space-between;
    border: 1px solid #ddd;
    text-align: center;
  }

  .price_modify>span{
    width: 28px;
    background: #eee;
    color: #a6a6a6;
  }

  .price_modify>input{
    border: none;
    width: 35px;
    text-align: center;
  }

  /*商品详情图片与最近预览*/
  .good-details>.el-row:nth-of-type(odd),.lightColor{/*奇数行*/
     background: #fff;
  }

  .good-details>.el-row:nth-of-type(even),.darkColor{/*偶数行*/
      background: #f7f7f7;
  }

  /*长图*/
  .longPic>div{
    width: 100%;
    height: 100%;
    font-size: 0;
  }


  .longPic img{
    width: 100%;
    height: 110%;
  }
</style>
