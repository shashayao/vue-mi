<template>
  <div id="app">
    <top-bar />
    <top-header />
    <top-banner />
  </div>
</template>

<script>
import TopBar from "./components/TopBar";
import TopHeader from "./components/TopHeader"
import TopBanner from "./components/TopBanner"
export default {
  name: "App",
  components: {
    TopBar,
    TopHeader,
    TopBanner
  },
};
</script>

<style>
@import "./assets/css/base.css";
</style>
