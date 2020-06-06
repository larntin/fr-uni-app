<template>
  <view style="height: 100%;">
    <view class="box">
      <view class="cu-bar bg-white">
        <view class="action">
          <text class="cuIcon-titles" :style="'color: '+themeColor+';'"></text>
          <text class="text-xl text-bold">一键切换主题色</text>
        </view>
      </view>
    </view>
    <view class="padding-xs flex align-center">
      <view class="flex-sub">
        <view style="padding: 10upx;">应用内切换，同理可配置其他颜色。应用启动会请求配置；</view>
      </view>
    </view>
    <view style="width: 690upx;margin-left: 30upx;">
      <view>
        <view>设置不同的tabbar只需修改 数组即可</view>

        <button style="margin-bottom: 20upx;" class="cu-btn bg-cyan text-white margin-lr-xs" @tap="setTabbar1()">
          首页 - 发布 - 关于我们
        </button>

        <button style="margin-bottom: 20upx;" class="cu-btn bg-cyan text-white margin-lr-xs" @tap="setTabbar2()">
          关于我们 - 产品中心 - 新闻中心 - 首页
        </button>

        <button style="margin-bottom: 20upx;" class="cu-btn bg-cyan text-white margin-lr-xs" @tap="setTabbar3()">
          还原
        </button>
      </view>
    </view>
  </view>
</template>

<script>
  import {
    mapState
  } from "vuex";
  let tabList = [{
      "iconPath": "/static/tabbar/a2.png",
      "selectedIconPath": "/static/tabbar/a1.png",
      "title": "首页",
      "page": "index"
    },
    {
      "iconPath": "/static/tabbar/b2.png",
      "selectedIconPath": "/static/tabbar/b1.png",
      "title": "产品中心",
      "page": "goods"
    },
    {
      "iconPath": "/static/tabbar/c2.png",
      "selectedIconPath": "/static/tabbar/c1.png",
      "title": "发布",
      "page": "contact",
      "size": "big"
    },
    {
      "iconPath": "/static/tabbar/d2.png",
      "selectedIconPath": "/static/tabbar/d1.png",
      "title": "新闻中心",
      "page": "news"
    },
    {
      "iconPath": "/static/tabbar/e2.png",
      "selectedIconPath": "/static/tabbar/e1.png",
      "title": "关于我们",
      "page": "about"
    }
  ]
  export default {
    computed: {
      ...mapState({
        themeColor: 'themeColor',
        textColor: 'textColor',
        descTextColor: "descTextColor",
        bannerDotColor: 'bannerDotColor',
        bannerDotActiveColor: "bannerDotActiveColor",
        articles: 'articles'
      })
    },
    data() {
      return {

      };
    },
    methods: {
      setTabbar1() {
        this.$store.commit("SET_TABBAR", [tabList[0], tabList[2], tabList[4]])
      },
      setTabbar2() {
        this.$store.commit("SET_TABBAR", [tabList[4], tabList[1], tabList[3], tabList[0]])
      },
      setTabbar3() {
        this.$store.commit("SET_TABBAR", tabList)
      }
    }
  };
</script>

<style lang="less"></style>
