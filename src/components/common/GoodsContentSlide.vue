<template>
  <div class="content" :class="content.type">
    <h3 class="title">{{content.title}}</h3>
    <div class="slide-wrap">
      <span class="slide-left" @click="slidePre">
        <i class="fa fa-chevron-left fa-fw icon-chevron-left"></i>
      </span>
      <span class="slide-right" @click="slideNext">
        <i class="fa fa-chevron-right fa-fw icon-chevron-right"></i>
      </span>
      <ul class="sub-content clearfix" :style="{marginLeft:marginLeft}">
        <li class="content-item" v-for="(it,ind) of content.list" :key="ind">
          <template v-if="it.type == 2">
            <p class="subdesc">{{it.desc1}}</p>
            <p class="subdesc">{{it.desc2}}</p>
            <a :href="it.sourceUrl"><p class="subbtn">{{it.btnTxt}}</p></a>
          </template>
          <template v-else>
            <p class="subtitle">{{it.title}}</p>
            <p class="subdesc">{{it.desc}}</p>
            <p class="subprice">{{it.price}}</p>
          </template>

          <img class="content-img" :src="it.imgUrl" />
        </li>
      </ul>
      <ul class="dot-list">
        <li class="dot-item" v-for="(item,index) in 4" :key="index">
          <span class="dot" :class="{active:currPage === index}"></span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "GoodsContentSlide",
  data() {
    return {
      currPage: 0,
      marginLeft: "",
    };
  },
  props: {
    content: { required: true, type: Object },
  },
  methods: {
    slidePre() {
      if (this.currPage > 0) {
        this.currPage--;
        this.marginLeft = -296 * this.currPage + "px";
      }
    },
    slideNext() {
      if (this.currPage < this.content.list.length-1) {
        this.currPage++;
        this.marginLeft = -296 * this.currPage + "px";
      }
    },
  },
};
</script>

<style scoped>
.content {
  width: 296px;
  height: 375px;
  padding-top: 30px;
  position: relative;
  overflow: hidden;
}
.content:hover {
  transform: translateY(-2px);
  box-shadow: 5px 5px 20px #ccc;
}
.content:hover .slide-left,
.content:hover .slide-right {
  opacity: 1;
}
.title {
  text-align: center;
  font-size: 16px;
}
.book {
  color: #ffac13;
  border-top: 1px solid #ffac13;
}
.theme {
  color: #83c44e;
  border-top: 1px solid #83c44e;
}
.game {
  color: #e53935;
  border-top: 1px solid #e53935;
}
.app {
  color: #2196f3;
  border-top: 1px solid #2196f3;
}
.slide-left,
.slide-right {
  position: absolute;
  background: #b0b0b0;
  top: 45%;
  padding: 15px 0;
  color: #fff;
  cursor: pointer;
  display: block;
  z-index: 2;
  opacity: 0;
}
.slide-left {
  left: 0;
}
.slide-right {
  right: 0;
}
.sub-content {
  width: 1200px;
}
.content-item {
  text-align: center;
  float: left;
  width: 296px;
  height: 326px;
  position: relative;
}
.subtitle {
  font-size: 20px;
  color: #333;
  margin: 0 0 10px;
}
.subdesc {
  font-size: 12px;
  color: #b0b0b0;
  width: 200px;
  margin: 0 auto 10px;
}
.subprice {
  font-size: 14px;
  color: #333;
  height: 16px;
}
.subbtn {
  width: 130px;
  height: 30px;
  line-height: 30px;
  font-size: 12px;
  margin: 0 auto;
  cursor: pointer;
}
.book .subbtn{
  border: 1px solid #ffac13;
}
.game .subbtn{
  border: 1px solid #e53935;
}
.theme .subbtn{
  border: 1px solid #83c44e;
}
.app .subbtn{
  border: 1px solid #2196f3;
}
.book .subbtn:hover{
  color: #fff;
  background: #ffac13;
}
.game .subbtn:hover{
  color: #fff;
  background: #e53935;
}
.theme .subbtn:hover{
  color: #fff;
  background: #83c44e;
}
.app .subbtn:hover{
  color: #fff;
  background: #2196f3;
}
.dot-list {
  width: 140px;
  position: absolute;
  bottom: 10px;
  left: 80px;
  text-align: center;
}
.dot-item {
  width: 10px;
  height: 10px;
  display: inline-block;
  margin: 0 10px;
}
.dot-item span {
  display: block;
  width: 6px;
  height: 6px;
  border-radius: 6px;
  background: #b0b0b0;
}
.dot-item .active {
  background: #fff;
  border: 2px solid #ff6700;
}
</style>