<template>
  <el-container>
    <my-header></my-header>
    <!--主体部分-->
    <el-main>
      <el-row :gutter="24">
        <el-col :span="12"><div class="grid-content bg-purple"></div></el-col>
        <el-col :span="12"><div class="grid-content bg-purple"></div></el-col>
      </el-row>
    </el-main>

    <el-footer>
      <my-footer></my-footer>
    </el-footer>
  </el-container>

</template>

<script>
    export default {
        name: "login"
    }
</script>

<style scoped>
  .el-main{
    width: 1200px;
    margin: 40px auto 0;
  }
</style>
