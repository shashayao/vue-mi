<template>
  <div class="goods-container">
    <goods-top-box />
    <goods-collocation />
    <goods-accessories />
    <goods-around />
    <recommend />
    <hot-product />
    <goods-content />
    <mi-video />
  </div>
</template>

<script>
import GoodsTopBox from "./GoodsTopBox";
import GoodsCollocation from "./GoodsCollocation";
import GoodsAccessories from "./GoodsAccessories";
import GoodsAround from "./GoodsAround";
import Recommend from "./Recommend";
import HotProduct from "./HotProduct";
import GoodsContent from "./GoodsContent";
import MiVideo from "./MiVideo"
export default {
  name: "Goods",
  components: {
    GoodsTopBox,
    GoodsCollocation,
    GoodsAccessories,
    GoodsAround,
    Recommend,
    HotProduct,
    GoodsContent,
    MiVideo,
  },
};
</script>

<style scoped>
.goods-container {
  width: 100%;
  height: auto;
  background: #f5f5f5;
  padding-bottom: 40px;
}
</style>