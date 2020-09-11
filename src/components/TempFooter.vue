<template>
  <div class="temp-footer clearfix">
    <div>
      <div class="footer-service">
        <ul class="service-list clearfix">
          <li>
            <span>
              <i class="fa fa-gavel"></i>1小时快修服务
            </span>
          </li>
          <li>
            <span>
              <i class="fa fa-history"></i>7天无条件退货
            </span>
          </li>
          <li>
            <span>
              <i class="fa fa-history"></i>15天免费换货
            </span>
          </li>
          <li>
            <span>
              <i class="fa fa-gift"></i>满150元包邮
            </span>
          </li>
          <li>
            <span>
              <i class="fa fa-location-arrow"></i> 520余家售后网点
            </span>
          </li>
        </ul>
      </div>
      <div class="footer-info">
        <ul class="clearfix">
          <li v-for="(item,index) of footInfo" :key="index" class="info-box">
            <h3>{{item.name}}</h3>
            <ul>
              <li v-for="(it,ind) of item.list" :key="ind" class="info-item">
                <a :href="it.sourceUrl">
                  <p>{{it.name}}</p>
                </a>
              </li>
            </ul>
          </li>
          <div class="footer-col">
            <h3>400-100-5678</h3>
            <p>
              周一至周日 8:00-18:00
              <br />（仅收市话费）
            </p>
            <span>24小时在线客服</span>
          </div>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      footInfo: [
        {
          name: "帮助中心",
          list: [
            {
              name: "账户管理",
              sourceUrl: "//www.mi.com/service/account/register/",
            },
            {
              name: "购物指南",
              sourceUrl: "//www.mi.com/service/buy/buytime/",
            },
            {
              name: "订单操作",
              sourceUrl: "//www.mi.com/service/order/sendprogress/",
            },
          ],
        },
        {
          name: "服务支持",
          list: [
            {
              name: "售后政策",
              sourceUrl: "//www.mi.com/service/exchange",
            },
            {
              name: "自助服务",
              sourceUrl: "http://fuwu.mi.com/",
            },
            {
              name: "相关下载",
              sourceUrl: "http://xiazai.mi.com/",
            },
          ],
        },
        {
          name: "线下门店",
          list: [
            {
              name: "小米之家",
              sourceUrl: "//www.mi.com/c/xiaomizhijia/",
            },
            {
              name: "服务网点",
              sourceUrl: "//www.mi.com/static/maintainlocation/",
            },
            {
              name: "零售网点",
              sourceUrl: "//www.mi.com/static/familyLocation/",
            },
          ],
        },
        {
          name: "关于小米",
          list: [
            {
              name: "了解小米",
              sourceUrl: "//www.mi.com/about",
            },
            {
              name: "加入小米",
              sourceUrl: "http://hr.xiaomi.com/",
            },
            {
              name: "联系我们",
              sourceUrl: "//www.mi.com/about/contact",
            },
          ],
        },
        {
          name: "关注我们",
          list: [
            {
              name: "新浪微博",
              sourceUrl: "http://e.weibo.com/xiaomishouji",
            },
            {
              name: "小米部落",
              sourceUrl:
                "http://xiaoqu.qq.com/mobile/share/index.html?url=http%3A%2F%2Fxiaoqu.qq.com%2Fmobile%2Fbarindex.html%3Fwebview%3D1%26type%3D%26source%3Dindex%26_lv%3D25741%26sid%3D%26_wv%3D5123%26_bid%3D128%26%23bid%3D10525%26from%3Dwechat",
            },
            {
              name: "官方微信",
              sourceUrl: "",
            },
          ],
        },
        {
          name: "特色服务",
          list: [
            {
              name: "F码通道",
              sourceUrl: "//order.mi.com/queue/f2code",
            },
            {
              name: "小米移动",
              sourceUrl: "//www.mi.com/mimobile/",
            },
            {
              name: "防伪查询",
              sourceUrl: "//order.mi.com/misc/checkitem",
            },
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
.temp-footer {
  width: 1226px;
  margin: 0 auto;
  height: auto;
}
.footer-service {
  padding: 27px 0;
  border-bottom: 1px solid #ccc;
}
.service-list li {
  text-align: center;
  width: 245px;
  height: 27px;
  line-height: 27px;
  float: left;
}
.service-list li i {
  font-size: 24px;
  margin-right: 15px;
}
.footer-info {
  padding: 27px 0;
  text-align: center;
}
.info-box {
  width: 160px;
  height: 120px;
  float: left;
}
.info-box h3 {
  font-size: 14px;
  font-weight: normal;
  margin-bottom: 30px;
}
.info-item p {
  font-size: 12px;
}
.footer-col {
  margin-left: 30px;
  margin-top: 20px;
  width: 200px;
  float: right;
  border-left: 1px solid #ccc;
  text-align: center;
}
.footer-col h3 {
  margin: 0;
  color: #ff6700;
  font-size: 22px;
}
.footer-col p {
  font-size: 12px;
  color: #333;
}
.footer-col span {
  margin-left:35px;
  font-size: 14px;
  display: block;
  color: #ff6700;
  width: 130px;
  height: 30px;
  line-height: 30px;
  border: 1px solid #ff6700;
}
</style>