<template>
  <el-footer  style="margin: 0 auto;  width: 1320px; ">
    <!--四个块 开始-->
    <el-row >
      <el-col :span="6">
        <ul class="footer_lists">
          <li></li>
          <li></li>
          <li></li>
          <li></li>
        </ul>
      </el-col>
    </el-row>
    <!--四个块 结束-->

    <!--微信二维码 开始-->
    <el-row style="margin: 0 auto; width: 800px;">
      <el-col :span="12">
        <div>
          <img src="../assets/img/footer/weixin.jpg" style="margin-right: 40px;">
          <img src="../assets/img/footer/app.jpg" >
        </div>
      </el-col>
      <el-col :span="12" class="footer_lists_a">
        <ul>
          <li><a href="#" class="footer_lists_a_strong">购物指南</a></li>
          <li><a href="#" class="footer_lists_a_a">购物指南</a></li>
          <li><a href="#" class="footer_lists_a_a">购物指南</a></li>
          <li><a href="#" class="footer_lists_a_a">购物指南</a></li>
        </ul>
        <ul>
          <li><a href="#" class="footer_lists_a_strong">购物指南</a></li>
          <li><a href="#" class="footer_lists_a_a">购物指南</a></li>
          <li><a href="#" class="footer_lists_a_a">购物指南</a></li>
          <li><a href="#" class="footer_lists_a_a">购物指南</a></li>
        </ul>
        <ul>
          <li><a href="#" class="footer_lists_a_strong">购物指南</a></li>
          <li><a href="#" class="footer_lists_a_a">购物指南</a></li>
          <li><a href="#" class="footer_lists_a_a">购物指南</a></li>
          <li><a href="#" class="footer_lists_a_a">购物指南</a></li>
        </ul>
      </el-col>
    </el-row>
    <!--微信二维码 结束-->
    <el-row>
      <hr style="border: 1px solid #eee;"/>
    </el-row>

    <!--版权 开始-->
    <el-row>
      <el-row style="text-align: center; color: #999; font-size: 14px;">
        <el-col :span="24">版权所有 ©2018上海天天鲜果电子商务有限公司  保留所有权利 | 沪ICP备12042163</el-col>
      </el-row>
      <el-row>
        <el-row style="width: 150px; margin: auto">
          <el-col :span="12">
            <div><a href="#" class="a_green" style="font-size: 14px;">天天果园</a></div>
          </el-col>
          <el-col :span="12">
            <div><a href="#" class="a_green" style="font-size: 14px;">鲜果网购</a></div>
          </el-col>
        </el-row>
      </el-row>
      <el-row>
        <el-row style="width: 150px; margin: auto">
          <el-col :span="12">
            <div><img src="../assets/img/footer/shgs.gif" alt=""></div>
          </el-col>
          <el-col :span="12">
            <div><img src="../assets/img/footer/wgdjp.png" style="width: 40px;height: 42px;"></div>
          </el-col>
        </el-row>
      </el-row>
    </el-row>
    <!--版权 结束-->
  </el-footer>
</template>

<script>
    export default {
        name: "my-footer"
    }
</script>

<style scoped>
  /*下方四个图片*/
  .footer_lists{
    margin-top: 50px;
    width: 1290px;
    display: flex;
    justify-content: space-between;
    padding: 20px 0;
    border-top: 1px solid #ddd;
    border-bottom: 1px solid #ddd;
  }
  .footer_lists>li:nth-of-type(1){
    background-position: 40px 0;
  }

  .footer_lists>li:nth-of-type(2){
    background-position: 40px -60px;
  }

  .footer_lists>li:nth-of-type(3){
    background-position: 40px -120px;
  }

  .footer_lists>li:nth-of-type(4){
    background-position: 40px -180px;
    border: none;
  }

  .footer_lists>li {
    width: 320px;
    height: 60px;
    border-right: 1px solid #ddd;
    padding: 0 50px;
    background: url('../assets/img/footer/footer_lists.png') no-repeat;
  }


  .footer_lists_a{
    width: 300px;
    display: flex;
    justify-content: space-between;
    font-size: 14px;
    line-height: 30px;
  }

  .footer_lists_a_a{
    line-height: 30px;
    font-size: 14px;
    color: #999;
  }

  .footer_lists_a_strong{
    font-size: 14px;
    font-weight: bold;
    color: #000;
  }
</style>
