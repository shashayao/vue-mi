<template>
  <div class="goods-right">
    <ul class="goods-right-content">
      <goods-item v-for="(item,index) of rightGoods.slice(0,7)" :key="index" :good-item="item">
        <slot>
          <div class="color-333">{{item.title}}</div>
          <div class="color-ff6700">{{item.price}}元</div>
          <div class="color-b0b0b0">{{item.heat}}人评论</div>
        </slot>
      </goods-item>
    </ul>
    <ul class="goods-right-small">
      <load-more v-if="lastGoods" :souceUrl="lastGoods.sourceUrl">
        <!-- 此处使用lastGoods需要if判断，否则会有警告(使用父组件的数据前，必须要判断，不然会警告) -->
        <template v-slot:up v-if="lastGoods">{{lastGoods.title.slice(0,4)}}...</template>
        <template v-slot:down v-if="lastGoods">{{lastGoods.price}}元</template>
        <template v-slot:icon v-if="lastGoods">
          <img :src="lastGoods.imgUrl" />
        </template>
      </load-more>
      <load-more class="load-more" v-if="lastGoods" :souceUrl="lastGoods.moreUrl"></load-more>
    </ul>
  </div>
</template>

<script>
import GoodsItem from "./GoodsItem";
import LoadMore from "./LoadMore";
export default {
  name: "GoodsRight",
  data() {
    return {};
  },
  props: {
    rightGoods: {
      required: true,
      type: Array,
    },
  },
  components: {
    GoodsItem,
    LoadMore,
  },
  computed: {
    lastGoods: function () {
      if (this.rightGoods && this.rightGoods.length > 0) {
        return this.rightGoods[this.rightGoods.length - 1];
      }
    },
  },
};
</script>

<style scoped>
.goods-right {
  position: relative;
  float: right;
  width: 992px;
}
.goods-right-content {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
}
.goods-right-small {
  position: absolute;
  bottom: 14px;
  right: 0;
  width: 234px;
  height: 300px;
}
.load-more {
  margin-top: 14px;
}
</style>