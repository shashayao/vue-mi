<template>
  <div class="video">
    <goods-top>
      <template v-slot:left>视频</template>
      <template v-slot:right>
        <a href="http://www.mi.com/video" class="top-right">
          查看全部
          <i class="sub-icon fa fa-fw fa-chevron-circle-right top-icon"></i>
        </a>
      </template>
    </goods-top>
    <div class="video-box clearfix">
      <ul class="video-list">
        <li v-for="(item,index) of videos" :key="index" class="video-item">
          <div class="video-img">
            <img :src="item.imgUrl" />
            <span class="video-play">
              <i class="fa fa-play play-icon"></i>
            </span>
          </div>
          <p class="video-title">{{item.title}}</p>
          <p class="video-desc">{{item.desc}}</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import GoodsTop from "./common/GoodsTop";
export default {
  name: "Video",
  components: {
    GoodsTop,
  },
  data() {
    return {
      videos: [
        {
          videoUrl:
            "http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1ODg5ODA0MA==",
          imgUrl: "http://i3.mifile.cn/a4/73d67577-cbc7-4bd0-8678-4b1e95f4f4dc",
          title: "红米年度品牌视频",
          desc: "一亿人喜爱你，是一种责任。",
        },
        {
          videoUrl:
            "http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1OTg3NjQ4OA==",
          imgUrl: "http://i3.mifile.cn/a4/f7e434fb-8ce4-4442-bf78-0d66e409dfc3",
          title: "小米笔记本Air最全介绍视频",
          desc: "带独立显卡的轻薄笔记本",
        },
        {
          videoUrl:
            "http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1OTg4NjY0OA==",
          imgUrl: "http://i3.mifile.cn/a4/e2df3ad8-4147-44e1-8a54-b6bcafdc6c66",
          title: "小米笔记本Air可靠性测试视频",
          desc: "小米笔记本Air是如何炼成的？",
        },
        {
          videoUrl:
            "http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTU2NDM3NjEzMg==",
          imgUrl: "http://i3.mifile.cn/a4/T1v3LgBTxv1RXrhCrK.jpg",
          title: "小米Max 绝美外观视频",
          desc: '6.44" 大屏黄金尺寸，看什么都震撼',
        },
      ],
    };
  },
};
</script>

<style scoped>
.video {
  width: 1226px;
  margin: 0 auto;
}
.top-right {
  display: inline-block;
  color: #424242;
  height: 58px;
  line-height: 58px;
}
.top-right:hover,.top-right:hover i{
  color: #ff6700;
}
.top-icon {
  color: #b0b0b0;
  font-size: 20px;
}
.video-list {
  text-align: center;
}
.video-item {
  background: #fff;
  float: left;
  width: 296px;
  cursor: pointer;
  margin-left: 14px;
}
.video-item:first-child {
  margin: 0;
}
.video-title {
  font-size: 14px;
  color: #333;
}
.video-desc {
  font-size: 12px;
  color: #b0b0b0;
}
.video-img{
  position: relative;
}
.video-play{
  display: block;
  position: absolute;
  bottom: 10px;
  border: 2px solid #fff;
  width: 32px;
  height: 20px;
  line-height: 20px;
  border-radius: 10px;
  z-index: 2;
  background: #333;
  left: 20px;
  text-align: center;
}
.play-icon{
  font-size: 12px;
  color: #fff;
}
.video-play:hover{
  background: #ff6700;
}
</style>