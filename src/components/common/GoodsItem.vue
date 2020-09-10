<template>
  <li>
    <span class="goods-discount" :class="goodItem.discountType">{{goodItem.discount}}</span>
    <a :href="goodItem.sourceUrl">
      <img :src="goodItem.imgUrl" class="goods-item" />
      <slot>
        <div class="color-333">{{goodItem.title}}</div>
        <div class="color-b0b0b0">{{goodItem.desc}}</div>
        <div class="color-ff6700">{{goodItem.price}}元</div>
      </slot>
    </a>
    <div class="review" v-show="goodItem.reviewStatus">
      <span>{{goodItem.reviewDesc}}</span>
      <span>来自于{{goodItem.reviewAuthor}}的评价</span>
    </div>
  </li>
</template>

<script>
export default {
  name: "GoodsItem",
  props: {
    goodItem: {
      type: Object,
      default() {
        return {};
      },
    },
  },
};
</script>

<style scoped>
li {
  background: #fff;
  height: 300px;
  width: 234px;
  margin-left: 14px;
  margin-bottom: 14px;
  position: relative;
  transition: all 0.3;
  display: inline-block;
}
li:hover {
  transform: translateY(-2px);
  box-shadow: 5px 5px 20px #ccc;
}
li:hover .review{
  height: 70px;
  opacity: 1;
}
.goods-item {
  width: 160px;
  height: 160px;
  margin: 30px auto auto auto;
  display: block;
}
.color-333 {
  font-size: 14px;
  height: 30px;
  text-align: center;
  line-height: 30px;
  color: #333;
}
.color-b0b0b0 {
  text-align: center;
  font-size: 12px;
  height: 30px;
  line-height: 30px;
  color: #b0b0b0;
}
.color-ff6700 {
  text-align: center;
  font-size: 14px;
  height: 30px;
  line-height: 30px;
  color: #ff6700;
}
.goods-discount {
  position: absolute;
  top: 3px;
  left: 85px;
  width: 64px;
  height: 20px;
  line-height: 20px;
  font-size: 12px;
  text-align: center;
  color: #fff;
}
.free {
  background: #ffac13;
}
.new {
  background: #83c44e;
}
.discount {
  background: #e53935;
}
.review {
  position: absolute;
  padding: 10px 34px;
  font-size: 12px;
  bottom: 0;
  left: 0;
  background: #ff6700;
  color: #fff;
  height: 0;
  opacity: 0;
  transition: all 0.3s;
}
.review span{
  display: block;
  line-height: 20px;
  text-align: center;
}
.review span:last-child{
  margin-top:10px;
}
</style>