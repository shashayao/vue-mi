<template>
  <div class="goods-box-container clearfix">
    <goods-top>
      <template v-slot:left>
        智能硬件
      </template>
      <template v-slot:right>
        <a href="http://www.mi.com/smart" class="top-right">
          查看全部
          <i class="sub-icon fa fa-fw fa-chevron-circle-right top-icon"></i>
        </a>
      </template>
    </goods-top>
    <div class="box-left">
      <a href="http://www.mi.com/scooter/">
        <img src="http://i3.mifile.cn/a4/124d82cc-cfce-44ab-b711-28b21be81683" alt />
      </a>
    </div>
    <div class="box-right">
      <ul>
        <goods-item v-for="(item,index) of goods" :key="index" :good-item="item"></goods-item>
      </ul>
    </div>
  </div>
</template>

<script>
import GoodsTop from "./common/GoodsTop";
import GoodsItem from "./common/GoodsItem"
export default {
  data() {
    return {
      goods: [
        {
          sourceUrl: "//item.mi.com/1161200059.html",
          imgUrl: "http://i3.mifile.cn/a4/T1rQAgB7Av1RXrhCrK.jpg",
          title: "小米路由器3",
          desc: "四天线设计，更安全更稳定",
          price: "149",
          discountType: "free",
          discount: "免邮费",
        },
        {
          sourceUrl: "//www.mi.com/mibicycle/",
          imgUrl: "http://i3.mifile.cn/a4/2b69b930-a2fd-4d09-a46a-8690cb79f764",
          title: "电助力折叠自行车",
          desc: "力矩传感电助力，让城市出行轻松有趣",
          price: "149",
          discountType: "new",
          discount: "新品",
        },
        {
          sourceUrl: "//www.mi.com/mitu/",
          imgUrl: "http://i1.mifile.cn/a1/pms_1464615180.86261317!220x220.jpg",
          title: "米兔智能故事机",
          desc: "能说会道，宝宝的好玩伴",
          price: "199",
          discountType: "new",
          discount: "新品",
        },
        {
          sourceUrl: "//www.mi.com/water2/",
          imgUrl: "//i3.mifile.cn/a4/T1zTK_Bbhv1RXrhCrK.jpg",
          title: "小米净水器",
          desc: "厨下式 RO反渗透直出纯净水，包邮包安装",
          price: "1999",
        },
        {
          sourceUrl: "//www.mi.com/ihealth/ ",
          imgUrl: "http://i1.mifile.cn/a1/T17FCQByWv1RXrhCrK!220x220.jpg",
          title: "iHealth智能血压计（蓝牙版）",
          desc: "送给父母的健康礼物 测血压仅需1步",
          price: "199",
        },
        {
          sourceUrl: "//www.mi.com/dianfanbao/",
          imgUrl: "http://i1.mifile.cn/a1/T1OVC_ByY_1RXrhCrK!220x220.jpg",
          title: "米家压力IH电饭煲",
          desc: "智能烹饪，3L 容量",
          price: "999",
        },
        {
          sourceUrl: "//item.mi.com/1163200015.html",
          imgUrl: "http://i1.mifile.cn/a1/pms_1470730028.12443689!220x220.jpg",
          title: "全系智能套装限时款",
          desc: "开启你的智能生活",
          price: "292",
          oldPrice: "325",
          discountType: "discount",
          discount: "享九折",
        },
        {
          sourceUrl: "//list.mi.com/accessories/tag?id=guangganban",
          imgUrl: "http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg",
          title: "小米手环 光感版",
          desc: "实时监测心率，科学运动",
          price: "99",
        },
      ],
    };
  },
  components:{
    GoodsTop,
    GoodsItem
  }
};
</script>

<style scoped>
.goods-box-container {
  padding-top: 60px;
  margin-bottom: 26px;
  width: 1226px;
  margin: 0 auto;
}

.top-right{
  display: inline-block;
  color: #424242;
  height: 58px;
  line-height: 58px;
}
.top-icon {
  color: #b0b0b0;
  font-size: 20px;
}
.top-right:hover,.top-right:hover i{
  color: #ff6700;
}
.box-left {
  float: left;
}
.box-left:hover,
.box-right ul li:hover {
  transform: translateY(-1px);
  box-shadow: 5px 5px 5px #ccc;
}
.box-right {
  float: right;
  width: 992px;
}
.box-right ul {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
}
</style>