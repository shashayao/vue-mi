<template>
  <div class="boxs-top">
    <span><slot name="left"></slot></span>
    <div><slot name="right"></slot></div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.boxs-top {
  height: 58px;
  width: 100%;
  line-height: 58px;
  color: #333;
  height: 58px;
}
.boxs-top span {
  font-size: 22px;
  font-weight: 200;
  float: left;
}
.boxs-top div{
  float: right;
}
</style>