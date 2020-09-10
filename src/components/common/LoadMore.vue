<template>
  <li>
    <a :href="souceUrl" class="moreA clearfix">
      <div class="more-left">
        <div>
          <slot name="up">浏览更多</slot>
        </div>
        <div class="more-hot">
          <slot name="down">热门</slot>
        </div>
      </div>
      <slot name="icon">
        <i class="fa fa-arrow-circle-right fa-4x icon-arrow"></i>
      </slot>
    </a>
  </li>
</template>

<script>
export default {
  name: "LoadMore",
  props: {
    souceUrl: String
  },
};
</script>

<style scoped>
li {
  height: 143px;
  width: 234px;
  background: #fff;
  transition: all 0.3;
}
li:hover {
  transform: translateY(-2px);
  box-shadow: 5px 5px 20px #ccc;
}
.moreA {
  display: block;
  padding-top: 35px;
  padding-left: 20px;
}

.moreA img {
  width: 70px;
  height: 70px;
}
.more-left {
  float: left;
  width: 100px;
  margin-right: 20px;
  font-size: 14px;
}
.more-left div {
  text-align: center;
  height: 35px;
  line-height: 35px;
}
.more-hot {
  color: #ff6700;
}
.icon-arrow {
  color: #ff6700;
  font-size: 4em;
}
</style>