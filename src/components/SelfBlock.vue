<template>
  <div id="self">
    <img src="../assets/touxiang.jpg" alt="">
    <div class="name">
      <span>{{name}}</span>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Self',
  data() {
    return {
      name: 'fxosleeping'
    }
  }
}
</script>
<style scoped>
#self{
  width: 100%;
  overflow: hidden;
  position: relative;
  text-align: center;
  font-size: 20px;
}
#self>img{
  position: absolute;
  border: 2px solid #fff;
  border-radius: 50%;
  width: 80px;
  top: 20px;
  left: 50%;
  margin-left: -40px;
  z-index: 99;
}
.name{
  margin-top: 60px;
  /* background-color: #19be6b; */
  background-color: #303133;
  font-weight: bold;
  border-radius: 5px;
  color: #fff;
  height: 80px;
  width: 100%;
}
.name span{
  display: inline-block;
  margin-top: 45px;
}
</style>
