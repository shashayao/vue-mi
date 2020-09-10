<template>
  <ul class="goods-left">
    <li v-for="(item,index) of leftGoods" :key="index">
      <a :href="item.sourceUrl">
        <img :src="item.imgUrl" />
      </a>
    </li>
  </ul>
</template>

<script>
export default {
  name:'GoodsLeft',
  props:{
    leftGoods:{
      required:true,
      type:Array
    }
  }
};
</script>

<style scoped>
.goods-left{
  float: left;
  width: 234px;
  height: auto;
}
.goods-left li{
  cursor: pointer;
  transition: all 0.3s;
}
.goods-left li img:hover{
  transform: translateY(-2px);
  box-shadow: 5px 5px 20px #ccc;
}
.goods-left img{
  width: 234px;
  height: 300px;
  margin-bottom: 15px;
}
</style>