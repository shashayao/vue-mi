<template>
  <div class="top-sub">
    <div class="sub-left">
      <ul>
        <li v-for="(item,index) of subsLeft" :key="index">
          <a :href="item.souceUrl">
            <i :class="item.icon" class="fa fa-fw sub-icon"></i>
            <span>{{item.name}}</span>
          </a>
        </li>
      </ul>
    </div>
    <ul class="sub-right">
      <li v-for="(item,index) of subsRight" :key="index" class="right-item">
        <a :href="item.souceUrl">
          <img :src="item.imgUrl" alt />
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TopSub",
  data() {
    return {
      subsLeft: [
        {
          name: "选购手机",
          souceUrl: "http://www.mi.com/compare/",
          icon: "fa-mobile",
        },
        {
          name: "企业团购",
          souceUrl: "http://qiye.mi.com/",
          icon: "fa-gift",
        },
        {
          name: "官翻产品",
          souceUrl: "http://item.mi.com/re",
          icon: "fa-refresh",
        },
        {
          name: "小米移动",
          souceUrl: "http://huanxin.mi.com/product/list",
          icon: "fa-credit-card",
        },
        {
          name: "以旧换新",
          souceUrl: "http://huanxin.mi.com/product/list",
          icon: "fa-recycle",
        },
        {
          name: "话费充值",
          souceUrl: "http://recharge.10046.mi.com/",
          icon: "fa-credit-card-alt",
        },
      ],
      subsRight: [
        {
          souceUrl: "http://hd.mi.com/y/08191p/index.html",
          imgUrl:
            "http://i3.mifile.cn/a4/1327d707-4f67-4c36-8ae5-3d7704c989eb",
        },
        {
          souceUrl: "http://item.mi.com/buyphone/redmipro/",
          imgUrl:
            "http://i3.mifile.cn/a4/c202123c-4197-4666-9793-2f1e156ab23a",
        },
        {
          souceUrl: "http://item.mi.com/static/buymipad",
          imgUrl:
            "http://i3.mifile.cn/a4/216f7f38-66ee-4c1b-8409-8d77cb64d386",
        },
      ],
    };
  },
};
</script>

<style scoped>
.top-sub{
  width: 1226px;
  margin: 14px auto 26px;
}
.sub-left{
  float: left;
  width: 234px;
  height: 170px;
  background: #5f5750;
}
.sub-left ul{
  width: 100%;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
.sub-left ul li{
  width: 77px;
  height: 85px;
}
.sub-left ul li a{
  color: rgba(255,255,255,0.7);
}
.sub-icon{
  width: 77px;
  height: 24px;
  font-size: 20px;
  margin: 18px 0 5px 0;
}
.sub-left ul li a span{
  width: 77px;
  height: 12px;
  display: inline-block;
  font-size: 12px;
  text-align: center;
}
.sub-left ul li a:hover{
  color: #fff;
}
.sub-right{
  display: flex;
  flex-wrap: nowrap;
  flex-direction: row;
}
.right-item{
  width: 316px;
  height: 170px;
  display: inline-block;
  margin-left: 15px;
}
.right-item img{
  width: 316px;
  height: 170px;
}
</style>