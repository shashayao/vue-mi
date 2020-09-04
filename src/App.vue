<template>
  <div id="app">
    <top-bar />
    <top-header />
  </div>
</template>

<script>
import TopBar from "./components/TopBar";
import TopHeader from "./components/TopHeader"
export default {
  name: "App",
  components: {
    TopBar,
    TopHeader
  },
};
</script>

<style>
@import "./assets/css/base.css";
</style>
