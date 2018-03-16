<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
  export default {
    name: 'App',
  }
</script>

<style>
/*#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}*/
  body{
    margin:0;
    box-sizing: border-box;
  }

  a{
    font-size: 12px;
    color: #999;
    text-decoration: none;
  }

  a.active{
    color:#64a131;
  }

  ul,p,h1,h2,h3,h4,h5,h6{
    padding: 0;
    margin: 0;
  }
  li{
    list-style: none;
    padding: 0;
    margin: 0;
  }

.el-row {
  margin-bottom: 20px;
}
.el-col {
  border-radius: 4px;
}
.bg-purple-dark {
  background: #99a9bf;
}
.bg-purple {
  background: #eee;
  color:#999;
}
.bg-purple-light {
  background: #e5e9f2;
}
.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
.row-bg {
  padding: 10px 0;
  background-color: #f9fafc;
}

.a_green{
  color: #64a131;
}

.el-row,.el-col{
  border-radius: 0;
}
.el-main{
  margin-top: 40px;
  padding: 0;
  overflow: hidden;
}

  .gray{
    color: #999;
  }
</style>
