<template>
  <div class="goods-container">
    <goods-top-box />
    <goods-collocation />
    <goods-accessories />
    <goods-around />
    <recommend />
    <hot-product />
    <goods-content />
  </div>
</template>

<script>
import GoodsTopBox from "./GoodsTopBox";
import GoodsCollocation from "./GoodsCollocation"
import GoodsAccessories from "./GoodsAccessories"
import GoodsAround from "./GoodsAround"
import Recommend from "./Recommend"
import HotProduct from "./HotProduct"
import GoodsContent from "./GoodsContent"
export default {
  name: "Goods",
  components: {
    GoodsTopBox,
    GoodsCollocation,
    GoodsAccessories,
    GoodsAround,
    Recommend,
    HotProduct,
    GoodsContent
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