<template>
  <div class="content" :class="content.type">
    <h3 class="title">{{item.title}}</h3>
    <div class="slide-wrap">
      <span>
        <i class="fa fa-chevron-left fa-fw icon-chevron-left"></i>
      </span>
      <span>
        <i class="fa fa-chevron-right fa-fw icon-chevron-right"></i>
      </span>
      <ul class="sub-content">
        <li class="content-item" v-for="(it,ind) of item.list" :key="ind">
          <p class="subtitle">{{it.title}}</p>
          <p class="subdesc">{{it.desc}}</p>
          <img class="content-img" :src="it.imgUrl" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name:'GoodsContentSlide',
  data(){
    return{
      
    }
  }
};
</script>

<style>
</style>