<template>
  <div class="hot-product">
    <goods-top>
      <template v-slot:left>热评产品</template>
    </goods-top>
    <div class="product-content clearfix">
      <ul class="product-list">
        <li class="product-item" v-for="(item,index) of hots" :key="index">
          <a :href="item.sourceUrl">
            <img :src="item.imageUrl" />
            <div class="review-author">
              <span class="item-review">{{item.review}}</span>
              <span class="item-auther">来自{{item.author}}的评价</span>
            </div>
            <div class="name-price">
              <span>{{item.name}}</span>
              <span class="sep">|</span>
              <span class="item-price">{{item.price}}元</span>
            </div>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import GoodsTop from "./common/GoodsTop";
export default {
  name: "HotProduct",
  components: {
    GoodsTop,
  },
  data() {
    return {
      hots: [
        {
          sourceUrl: "//www.mi.com/mituwatch/",
          imageUrl:
            "http://i3.mifile.cn/a4/1e737b55-91bd-4f5b-b085-405fa722142f",
          review: "很好，孩子很喜欢，产品不错",
          author: "showen",
          name: "米兔儿童电话手表",
          price: "299",
        },
        {
          sourceUrl: "//www.mi.com/mitu/",
          imageUrl:
            "http://i3.mifile.cn/a4/032d0ff1-f77f-4830-a469-f3564d55e0c5",
          review:
            "米兔真心不错！！内容丰富，声音柔和，孩子看见后，就抱着不撒手啦，超级喜欢！！！",
          author: "Jack伯爵",
          name: "米兔智能故事机",
          price: "199",
        },
        {
          sourceUrl: "//www.mi.com/note3/pro/",
          imageUrl:
            "http://i3.mifile.cn/a4/a14bd55a-2a7f-4e5f-9d8d-79e3e1bdb467",
          review:
            "手机很不错 外观大气金属质感 一直都用的红米手机 很不错 很漂亮也很好用",
          author: "1108656217",
          name: "红米Note 3全网通版",
          price: "899",
        },
        {
          sourceUrl: "//www.mi.com/miwifi3/",
          imageUrl:
            "http://i3.mifile.cn/a4/8949026b-fa9a-4370-989b-5d5e2f149106",
          review:
            "我就是喜欢这样的路由器，我每天回到家都要连着WiFi上网，上班就没办法连着呢！每次都等待着下班，我好...",
          author: "欧阳长",
          name: "小米路由器3",
          price: "149",
        },
      ],
    };
  },
};
</script>

<style scoped>
.hot-product {
  width: 1226px;
  margin: 0 auto;
}
.product-content {
  font-size: 14px;
}
.product-content ul{
  transition: all 0.3s;
}
.product-content ul li {
  width: 296px;
  height: 415px;
  display: inline-block;
  margin-left: 14px;
  background: #fff;
}
.product-content ul li:hover{
  transform: translateY(-2px);
  box-shadow: 5px 5px 10px #ccc;
}
.product-content ul li:first-child {
  margin-left: 0;
}
.review-author {
  width: 296px;
  height: 112px;
}
.item-review{
  line-height: 24px;
  height: 72px;
  display: block;
  margin: 22px 28px;
}
.item-auther{
  margin-left: 22px;
  font-size: 12px;
  color: #b0b0b0;
}
.name-price{
  margin: 10px 0 0 22px;
  
}
.product-content img {
  width: 296px;
  height: 220px;
}
.sep{
  margin: 0 10px;
  color: #ccc;
}
.item-price{
  color: #ff6700;
}
</style>