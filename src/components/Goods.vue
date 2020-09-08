<template>
  <div class="goods-container">
    <goods-top-box />
  </div>
</template>

<script>
import GoodsTopBox from "./GoodsTopBox";
export default {
  name: "Goods",
  components: {
    GoodsTopBox,
  },
};
</script>

<style scoped>
.goods-container{
  width: 100%;
  height: auto;
  background: #f5f5f5;
}
</style>