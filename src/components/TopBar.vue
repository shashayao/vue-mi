<template>
  <header class="top-container">
    <div class="top-bar clearfix">
      <div class="topbar-nav">
        <ul>
          <li v-for="item of navs" :key="item.name" class="nav clearfix">
            <a href="item.souceUrl" class="nav-name">{{item.name}}</a>
            <span class="nav-separate">|</span>
          </li>
        </ul>
      </div>
      <div class="topbar-info">
        <a href="http://order.mi.com/site/login?redirectUrl=http://www.mi.com/index.html">登录</a>
        <span>|</span>
        <a href="https://account.xiaomi.com/pass/register">注册</a>
      </div>
      <div class="topbar-cart">
        <div class="cart" @mouseleave="evtCartOut" @mouseenter="evtCartEnter">
          <a href="http://static.mi.com/cart/">
            <i class="fa fa-cart-arrow-down"></i>
            购物车（{{cartnum}}）
          </a>
        </div>
        <!-- <div class="cart-list" transition="fadein" v-show="cartList">购物车中还没有商品，赶快选购吧！</div> -->
        <transition name="fade">
          <div class="cart-list" v-show="cartList">购物车中还没有商品，赶快选购吧！</div>
        </transition>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "TopBar",
  data() {
    return {
      navs: [
        { name: "小米商城", sourceUrl: "http://www.mi.com/index.html" },
        { name: "MIUI", sourceUrl: "http://www.miui.com/" },
        { name: "米聊", sourceUrl: "http://www.miliao.com/" },
        { name: "游戏", sourceUrl: "http://game.xiaomi.com/" },
        { name: "多看阅读", sourceUrl: "http://www.duokan.com/" },
        { name: "云服务", sourceUrl: "https://i.mi.com/" },
        { name: "小米网移动版", sourceUrl: "http://www.mi.com/c/appdownload/" },
        { name: "问题反馈", sourceUrl: "http://static.mi.com/feedback/" },
        { name: "Select Region", sourceUrl: "http://www.mi.com/index.html" },
      ],
      cartnum: 0,
      cartList: false,
    };
  },
  methods: {
    evtCartEnter() {
      this.cartList = true;
    },
    evtCartOut() {
      this.cartList = false;
    },
  },
};
</script>

<style scoped>
.top-container {
  width: 100%;
  height: 40px;
  background: #333;
}
.top-bar {
  width: 1226px;
  margin: 0 auto;
  font-size: 12px;
  position: relative;
}
.topbar-nav {
  float: left;
  height: 40px;
  line-height: 40px;
  /* overflow: hidden; */
}
.topbar-info {
  position: absolute;
  top: 13px;
  right: 140px;
}
.topbar-cart {
  float: right;
  height: 40px;
  line-height: 40px;
  width: 120px;
  position: relative;
}
.topbar-nav ul,
.topbar-info {
  display: inline-block;
  padding: 0;
  margin: 0;
}
.topbar-nav ul li {
  display: inline-block;
  height: 40px;
  line-height: 40px;
}
li:not(:nth-child(1)) {
  padding-left: 5px;
}
.topbar-nav ul .nav .nav-name,
.topbar-info a,
.topbar-info span {
  color: #b0b0b0;
}
.topbar-nav ul .nav .nav-name:hover,
.topbar-info a:hover {
  color: #fff;
}
li:nth-child(9) .nav-separate {
  display: none;
}
.nav-separate {
  margin-left: 5px;
  color: #b0b0b0;
}
.cart {
  background: #424242;
}
.cart i {
  font-size: 20px;
  position: absolute;
  top: 10px;
  left: 15px;
  color: #b0b0b0;
}

.cart a {
  width: 100%;
  height: 100%;
  display: block;
  color: #b0b0b0;
  padding-left: 40px;
  position: relative;
}
.cart:hover {
  background: #fff;
}
.cart a:hover i,
.cart a:hover {
  color: #ff6700;
}
.cart-list {
  position: absolute;
  width: 316px;
  height: 96px;
  line-height: 96px;
  top: 40px;
  right: 0;
  box-shadow: 0 0 5px #ccc;
  text-align: center;
  color: #b0b0b0;
  z-index: 99;
  background: #fff;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>