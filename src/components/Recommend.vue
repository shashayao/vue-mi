<template>
  <div class="recommend">
    <goods-top>
      <template v-slot:left>为你推荐</template>
      <template v-slot:right>
        <div class="control-part">
          <span @click="slidePre" :class="{disable:currPage === 0}">
            <i class="fa fa-chevron-left icon-arrow"></i>
          </span>
          <!-- 使用data数据不用加this -->
          <span
            @click="slideNext"
            :class="{disable:currPage === Math.floor((recommends.length-1)/5)}"
          >
            <i class="fa fa-chevron-right icon-arrow"></i>
          </span>
        </div>
      </template>
    </goods-top>
    <div class="recommend-wrap">
      <ul :style="{marginLeft:currM+'px'}">
        <goods-item v-for="(item,index) of recommends" :key="index" :good-item="item">
          <slot>
            <div class="color-333">{{item.name}}</div>
            <div class="color-ff6700">{{item.price}}元</div>
            <div class="color-b0b0b0">{{item.favorable}}人评论</div>
          </slot>
        </goods-item>
      </ul>
    </div>
  </div>
</template>

<script>
import GoodsTop from "./common/GoodsTop";
import GoodsItem from "./common/GoodsItem";
export default {
  name: "",
  components: {
    GoodsTop,
    GoodsItem,
  },
  data() {
    return {
      recommends: [
        {
          sourceUrl: "//item.mi.com/1154300011.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1.VVgBjAT1RXrhCrK.jpg?width=140&height=140",
          name: "小米电视主机",
          price: "999",
          favorable: "102",
        },
        {
          sourceUrl: "//item.mi.com/1153300030.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1LrdvBbAT1RXrhCrK.jpg?width=140&height=140",
          name: "小米手环",
          price: "69",
          favorable: "11.8万",
        },
        {
          sourceUrl: "//item.mi.com/1155100006.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1_tEgBmVv1RXrhCrK.jpg?width=140&height=140",
          name: "米兔儿童电话手表",
          price: "299",
          favorable: "7865",
        },
        {
          sourceUrl: "//item.mi.com/1154100018.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1TpZ_ByYv1R4cSCrK.png?width=140&height=140",
          name: "小米低音炮",
          price: "599",
          favorable: "4908",
        },
        {
          sourceUrl: "//item.mi.com/1155100011.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1CDbjBgAT1RXrhCrK.jpg?width=140&height=140",
          name: "90分旅行箱 24寸",
          price: "349",
          favorable: "1.1万",
        },
        {
          sourceUrl: "//item.mi.com/1154900069.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1PyZ_Bjdv1RXrhCrK.jpg?width=140&height=140 ",
          name: "小米智能插座 基础版",
          price: "49",
          favorable: "8622",
        },
        {
          sourceUrl: "//item.mi.com/1162100021.html",
          imgUrl:
            "//i1.mifile.cn/a1/pms_1464071511.37197399.jpg?width=140&height=140",
          name: "米家 LED 智能台灯",
          price: "169",
          favorable: "4268人好评",
        },
        {
          sourceUrl: "//item.mi.com/1153700018.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1Ay_gBKKv1RXrhCrK.jpg?width=140&height=140",
          name: "90分旅行箱 20寸",
          price: "299",
          favorable: "1.5万",
        },
        {
          sourceUrl: "//item.mi.com/1161200004.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1WxYvB_xv1RXrhCrK.jpg?width=140&height=140",
          name: "小米活塞耳机 基础版",
          price: "29",
          favorable: "5.5万",
        },
        {
          sourceUrl: "//item.mi.com/1153300025.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1tzL_BjYT1RXrhCrK.jpg?width=140&height=140",
          name: "学院风简约双肩包",
          price: "59",
          favorable: "1.8万",
        },
        {
          sourceUrl: "//item.mi.com/1154300036.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1F5K_BjVv1RXrhCrK.jpg?width=140&height=140",
          name: "小米小钢炮蓝牙音箱2",
          price: "129",
          favorable: "1.2万",
        },
        {
          sourceUrl: "//item.mi.com/1162900011.html",
          imgUrl:
            "//i1.mifile.cn/a1/pms_1470793898.34754317.jpg?width=140&height=140",
          name: "90分金属旅行箱",
          price: "1799",
          favorable: "23",
        },
        {
          sourceUrl: "//item.mi.com/1153800044.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1MDK_B_YT1RXrhCrK.jpg?width=140&height=140",
          name: "小米蓝牙音箱",
          price: "199",
          favorable: " 1.9万",
        },
        {
          sourceUrl: "//item.mi.com/1161200013.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1FtKgBvZv1RXrhCrK.jpg?width=140&height=140",
          name: "小米多功能都市休闲胸包",
          price: "69",
          favorable: "9453",
        },
        {
          sourceUrl: "//item.mi.com/1161800001.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1HQA_BCd_1RXrhCrK.jpg?width=140&height=140",
          name: "米家iHealth血压计",
          price: "399",
          favorable: "1529",
        },
        {
          sourceUrl: "//item.mi.com/1153900041.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1JJ__BbYT1RXrhCrK.jpg?width=140&height=140",
          name: "小米净水器滤芯",
          price: "59",
          favorable: "6640",
        },
        {
          sourceUrl: "//item.mi.com/1162800007.html",
          imgUrl:
            "//i1.mifile.cn/a1/pms_1468287589.40786199.jpg?width=140&height=140",
          name: "米家随身风扇",
          price: "19.9",
          favorable: "4522",
        },
        {
          sourceUrl: "//item.mi.com/1160800073.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1N5KjB_dT1RXrhCrK.jpg?width=140&height=140",
          name: "小米家庭音响 金属版",
          price: "899",
          favorable: "0",
        },
        {
          sourceUrl: "//item.mi.com/1161000003.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1LpWjB4bv1RXrhCrK.jpg?width=140&height=140",
          name: "小米空气净化器滤芯 经济版",
          price: "129",
          favorable: "473",
        },
        {
          sourceUrl: "//item.mi.com/1161200073.html",
          imgUrl:
            "//i1.mifile.cn/a1/T1bED_B__v1RXrhCrK.jpg?width=140&height=140",
          name: "小蚁摄像机储存套装（夜视+8GB）",
          price: " 165.9",
          favorable: "0",
        },
      ],
      currPage: 0,
      currM:''
    };
  },
  methods: {
    slideNext() {
      if (this.currPage < Math.floor((this.recommends.length - 1) / 5)) {
        this.currPage++;
        this.currM = this.currPage * (-1226);
      }
    },
    slidePre() {
      if (this.currPage > 0) {
        this.currPage--;
        this.currM = this.currPage * (-1226);
      }
    },
  },
};
</script>

<style scoped>
.recommend {
  width: 1226px;
  margin: 0 auto;
}
.recommend-wrap {
  width: 1226px;
  height: 310px;
  overflow: hidden;
}
.recommend-wrap ul{
  width: auto;
  height: 300px;
  transition: all 0.2s;
}
.recommend-wrap ul li:nth-child(5n+1) {
  margin-left: 0;
}
.control-part .disable {
  border: 1px solid #e0e0e0;
}
.control-part .disable i {
  color: #e0e0e0;
}
.control-part span {
  cursor: pointer;
  display: block;
  width: 34px;
  height: 23px;
  border: 1px solid #ccc;
  position: relative;
  margin-top: 14px;
}

.icon-arrow {
  color: #b0b0b0;
  font-size: 10px;
  position: absolute;
  right: 12px;
  top: 6px;
}
</style>