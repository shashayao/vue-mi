<template>
  <div id="app">
    <top-bar />
    <top-header />
    <top-banner />
    <top-sub />
    <goods />
  </div>
</template>

<script>
import TopBar from "./components/TopBar";
import TopHeader from "./components/TopHeader"
import TopBanner from "./components/TopBanner"
import TopSub from "./components/TopSub"
import Goods from "./components/Goods"
export default {
  name: "App",
  components: {
    TopBar,
    TopHeader,
    TopBanner,
    TopSub,
    Goods
  },
};
</script>

<style>
@import "./assets/css/base.css";
</style>
