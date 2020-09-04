<template>
  <div class="top-header">
    <div class="container">
      <a class="icon-mi"></a>
      <a class="pic-gif"></a>
      <div class="header-navs">
        <ul class="navs">
          <li
            v-for="(item,index) of navs"
            :key="index"
            class="nav-item"
            @mouseenter="evtLiEnter(item.type)"
            @mouseleave="evtLiLeave"
          >
            <a href>{{item.name}}</a>
          </li>
        </ul>
      </div>
      <div class="header-search" :class="{'search-active':searchActive}">
        <transition name="fade">
          <ul class="hot-words" v-show="hotItemsShow">
            <li v-for="(item,index) of hotItems" :key="index">{{item}}</li>
          </ul>
        </transition>
        <input type="search" name="search" @focus="evtIptFocus" @blur="evtIptBlur" />
        <label for="search" class="search-btn" :class="{'label-active':searchActive}">
          <i class="icon-search"></i>
        </label>
      </div>
      <div class="search-result" v-show="searchActive">
        <ul>
          <li v-for="(item,index) of results" :key="index">
            <span class="result-left">{{item.name}}</span>
            <span class="result-right">约有{{item.number}}件</span>
          </li>
        </ul>
      </div>
    </div>
    <!-- <transition name="fade"> -->
      <div class="header-menu" v-show="headerMenuShow"  @mouseenter="evtLiEnter()"
            @mouseleave="evtLiLeave()">
        <ul>
          <li v-for="(item,index) of currentNav" :key="index">
            <a :href="item.sourcePath">
              <img :src="item.imgUrl" />
            </a>
            <div class="menu-name">{{item.name}}</div>
            <div class="menu-price">{{item.price}}</div>
          </li>
        </ul>
      </div>
    <!-- </transition> -->
  </div>
</template>

<script>
export default {
  name: "TopHeader",
  data() {
    return {
      navs: [
        { name: "小米手机", type: "xiaomi" },
        { name: "红米", type: "red" },
        { name: "平板 · 笔记本", type: "flats" },
        { name: "电视", type: "tv" },
        { name: "盒子 · 影音", type: "box" },
        { name: "路由器", type: "router" },
        { name: "智能硬件", type: "hardware" },
        { name: "服务", sourceUrl: "//www.mi.com/service/" },
        { name: "社区", sourceUrl: "http://www.xiaomi.cn" },
      ],
      xiaomi: [
        {
          name: "小米Max",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/maxdingbu!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "1299元起",
        },
        {
          name: "小米手机5",
          imgUrl: "http://c1.mifile.cn/f/i/16/goods/nav/mi5!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "1499元起",
        },
        {
          name: "小米手机4c",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mi4c!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "1099元",
        },
      ],
      red: [
        {
          name: "红米pro",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/cn-index/hongmipro-320!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "1499元起",
        },
        {
          name: "红米note3",
          imgUrl: "http://c1.mifile.cn/f/i/g/2015/video/hongmi3s!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "899元起",
        },
        {
          name: "红米手机3S",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/note3!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "699元起",
        },
        {
          name: "红米手机3",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/hongmi3!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "699元起",
        },
        {
          name: "红米手机3X",
          imgUrl: "http://c1.mifile.cn/f/i/g/doodle/320-220!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "799元",
        },
      ],
      flats: [
        {
          name: "小米平板2 16GB",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/cn-index/hongmipro-320!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "999元",
        },
        {
          name: "小米平板2 64GB",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mipad2-64!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "1299元",
        },
        {
          name: "小米平板2 64GB Windows版",
          imgUrl:
            "http://c1.mifile.cn/f/i/15/goods/nav/mipad2-64-win!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "1299元",
        },
        {
          name: "小米笔记本Air 12.5",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/video/bijiben32012.5!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "3499元",
        },
        {
          name: "小米笔记本Air 13.3",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/cn-index/bijiben320!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "4999元",
        },
      ],
      tv: [
        {
          name: "小米电视3S 43英寸",
          imgUrl: "http://c1.mifile.cn/f/i/16/goods/nav/mitv3s-43!160x110.jpg",
          sourcePath: "http://www.mi.com/mitv3s/43/",
          price: "1499元",
        },
        {
          name: "小米电视3S 48英寸",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mitv3s48!160x110.jpg",
          sourcePath: "http://www.mi.com/mitv3s/48/",
          price: "1999元",
        },
        {
          name: "小米电视3 55英寸",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mitv355!160x110.jpg",
          sourcePath: "http://www.mi.com/mitv3/55/",
          price: "3299元起",
        },
        {
          name: "小米电视3 60英寸",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mitv3-60!160x110.jpg",
          sourcePath: "http://www.mi.com/mitv3/60/",
          price: "3499元",
        },
        {
          name: "小米电视3S 65英寸 曲面",
          imgUrl: "http://c1.mifile.cn/f/i/16/goods/nav/mitv3s-65!160x110.jpg",
          sourcePath: "http://www.mi.com/mimax/",
          price: "8999元",
        },
        {
          name: "小米电视3 70英寸",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mitv70!160x110.jpg",
          sourcePath: "http://www.mi.com/mitv3/70/",
          price: "8999元",
        },
      ],
      box: [
        {
          name: "小米盒子mini版",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/hezimini.png",
          sourcePath: "http://www.mi.com/hezimini/",
          price: "179元",
        },
        {
          name: "小米盒子3",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/hezi3.png",
          sourcePath: "http://www.mi.com/hezi3/",
          price: "249元",
        },
        {
          name: "小米盒子3 增强版",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/hezi3s!160x110.jpg",
          sourcePath: "http://www.mi.com/hezi3s/",
          price: "399元",
        },
        {
          name: "小米电视主机",
          imgUrl: "http://c1.mifile.cn/f/i/g/2015/cn-index/zhuji!160x110.jpg",
          sourcePath: "http://www.mi.com/tvzj/",
          price: "999元",
        },
        {
          name: "小米家庭音响 金属版",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/cn-index/jinshuban!160x110.jpg",
          sourcePath: "http://item.mi.com/1160800073.html",
          price: "899元",
        },
        {
          name: "小米家庭音响 标准版",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/cn-index/putonban!160x110.jpg",
          sourcePath: "http://item.mi.com/1160800074.html",
          price: "699元",
        },
      ],
      router: [
        {
          name: "全新小米路由器",
          imgUrl: "http://c1.mifile.cn/f/i/16/goods/nav/mitv3s-43!160x110.jpg",
          sourcePath: "http://www.mi.com/mitv3s/43/",
          price: "699元起",
        },
        {
          name: "小米路由器 3",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/miwifi-3!160x110.jpg",
          sourcePath: "http://www.mi.com/miwifi3/",
          price: "149元",
        },
        {
          name: "小米路由器 mini",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/miwifimini!160x110.jpg",
          sourcePath: "http://www.mi.com/miwifimini/",
          price: "119元",
        },
        {
          name: "小米路由器 3C",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/mitv3-60!160x110.jpg",
          sourcePath: "http://www.mi.com/mitv3/60/",
          price: "99元",
        },
        {
          name: "小米路由器 青春版",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/miwifilite!160x110.jpg",
          sourcePath: "http://www.mi.com/miwifilite/",
          price: "69元",
        },
        {
          name: "小米WiFi放大器",
          imgUrl:
            "http://c1.mifile.cn/f/i/15/goods/nav/wifiExtension!160x110.jpg",
          sourcePath: "http://item.mi.com/1153200003.html",
          price: "35元",
        },
      ],
      hardware: [
        {
          name: "九号平衡车",
          imgUrl: "http://c1.mifile.cn/f/i/15/goods/nav/scooter!160x110.jpg",
          sourcePath: "http://www.mi.com/scooter/",
          price: "1999元",
        },
        {
          name: "小米净水器",
          imgUrl: "http://c1.mifile.cn/f/i/g/2015/cn-index/water2!160x110.jpg",
          sourcePath: "http://www.mi.com/water/",
          price: "1299元起",
        },
        {
          name: "米家压力IH电饭煲",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/2015/cn-index/dianfanbao!160x110.jpg",
          sourcePath: "http://www.mi.com/dianfanbao/",
          price: "999元",
        },
        {
          name: "小米空气净化器 2",
          imgUrl: "http://c1.mifile.cn/f/i/16/goods/nav/air2!160x110.jpg",
          sourcePath: "http://www.mi.com/air2/",
          price: "649元",
        },
        {
          name: "智能摄像机",
          imgUrl:
            "http://c1.mifile.cn/f/i/g/doodle/zhinengyingjian!160x110.jpg",
          sourcePath: "http://list.mi.com/accessories/tag?id=shexiangji",
          price: "149元起",
        },
      ],
      searchActive: false,
      hotItems: ["红米pro", "小米笔记本air"],
      hotItemsShow: true,
      results: [
        { name: "小米手机5", number: "11" },
        { name: "空气净化器2", number: "1" },
        { name: "活塞耳机", number: "4" },
        { name: "小米路由器", number: "8" },
        { name: "移动电源", number: "21" },
        { name: "运动相机", number: "3" },
        { name: "小米摄像机", number: "2" },
        { name: "小米体重秤", number: "1" },
        { name: "小米插线板", number: "13" },
        { name: "配件优惠套装", number: "32" },
      ],
      currentNav: this.xiaomi,
      headerMenuShow: false,
    };
  },
  methods: {
    evtIptFocus() {
      this.searchActive = true;
      this.hotItemsShow = false;
    },
    evtIptBlur() {
      this.searchActive = false;
      this.hotItemsShow = true;
    },
    evtLiEnter(type) {
      this.currentNav = this[type];
      this.headerMenuShow = true;
    },
    evtLiLeave() {
      this.headerMenuShow = false;
    },
  },
};
</script>

<style scoped>
.top-header {
  width: 100%;
  height: 100px;
}
.container {
  position: relative;
  width: 1226px;
  height: 100%;
  margin: 0 auto;
  display: flex;
  flex-flow: row;
  align-items: center;
}
.icon-mi {
  width: 55px;
  height: 55px;
  background: url("../assets/img/icon-mi.png");
  background-size: 100% 100%;
}
.pic-gif {
  width: 163px;
  height: 66px;
  background: url("../assets/img/win.gif");
  background-size: 100% 100%;
  margin-left: 10px;
}
.nav-item {
  display: inline-block;
  padding: 0 10px;
  font-size: 16px;
  height: 88px;
  line-height: 88px;
}
.nav-item a:hover {
  color: #ff6700;
}
.header-search {
  position: absolute;
  right: 0;
  width: 295px;
  height: 50px;
  border: 1px solid #e0e0e0;
  top: 23px;
}
.header-search input {
  float: left;
  height: 100%;
  width: 240px;
  outline: none;
  border: 0;
}
.search-btn {
  display: block;
  float: right;
  width: 50px;
  height: 100%;
  border-left: 1px solid #e0e0e0;
  cursor: pointer;
}
.icon-search {
  background: url("../assets/img/icon-search.png");
  height: 20px;
  width: 20px;
  background-size: 100% 100%;
  display: block;
  margin: 15px 0 0 15px;
}
.search-btn:hover {
  background: #ff6700;
}
.search-btn:hover .icon-search {
  background: url("../assets/img/icon-search-white.png");
  background-size: 100% 100%;
}
.search-active {
  border: 1px solid #ff6700;
}
.label-active {
  border-left: 1px solid #ff6700;
}
.hot-words {
  position: absolute;
  font-size: 12px;
  text-align: right;
  top: 16px;
  right: 60px;
}
.hot-words li {
  display: inline-block;
  padding: 3px;
  margin-right: 5px;
  background: #eee;
  color: #757575;
  cursor: pointer;
}
.hot-words li:hover {
  background: #ff6700;
  color: #fff;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.search-result {
  position: absolute;
  right: 51px;
  top: 75px;
  border-left: 1px solid #ff6700;
  border-right: 1px solid #ff6700;
  border-bottom: 1px solid #ff6700;
  width: 244px;
}
.search-result li {
  height: 30px;
  font-size: 12px;
  line-height: 30px;
  padding: 0 10px;
}
.search-result li span {
  display: inline-block;
}
.result-left {
  float: left;
}
.result-right {
  float: right;
  color: #b0b0b0;
}
.header-menu {
  position: absolute;
	left: 0;
	top: 140px;
	width: 100%;
	height: 230px;
	background: #fff;
	box-shadow: 0 1px 5px #ccc;
	z-index: 11;
}
.header-menu ul {
  width: 1500px;
  margin: 0 auto;
  height: 100%;
  display: flex;
}
.header-menu ul li {
  margin-top: 40px;
  width: 200px;
  text-align: center;
}
.header-menu ul li:not(:last-child) a {
  display: inline-block;
  border-right: 1px solid #ccc;
  width: inherit;
}
.header-menu ul li a img {
  width: 160px;
  height: 110px;
}
.header-menu ul li div {
  height: 25px;
  line-height: 25px;
  font-size: 12px;
  text-align: center;
}
.menu-name {
  margin-top: 10px;
}
.menu-price {
  color: #ff6700;
}
</style>