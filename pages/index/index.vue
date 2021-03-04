<template>
  <view class="container">
    <!-- header-info -->
    <view class="header-info">
      <view class="info-left">
        <view class="info-name">
          <text>Hi {{ userInfo.name }}</text>
        </view>
        <view class="info-targets-wrapper">
          <text
            >你有<text class="info-targets">{{ userInfo.targets }}</text
            >个待办</text
          >
        </view>
      </view>
      <view class="info-right">
        <view class="img-msg-wrapper">
          <cover-image
            class="img-msg"
            src="/static/image/msg.png"
          ></cover-image>
        </view>
        <view class="img-portrait-wrapper">
          <cover-image
            class="img-portrait"
            src="/static/image/portrait.png"
          ></cover-image>
        </view>
      </view>
    </view>

    <!-- 头部滚动 -->
    <view>
      <view class="scroll-view-position">
        <text class="scroll-text">你的代办项</text>

        <scroll-view
          class="scroll-view_h"
          scroll-x="true"
          @scroll="scroll"
          scroll-left="120"
        >
          <view class="scroll-view">A</view>
          <view class="scroll-view">B</view>
          <view class="scroll-view">C</view>
        </scroll-view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      userInfo: {
        name: "hermine",
        targets: 5,
      },
    };
  },
  onLoad() {},
  methods: {},
};
</script>

<style>
.container {
  height: 100vh;
  background-color: #f2dfdb;
}
.header-info {
  display: flex;
  justify-content: space-between;
  height: 100px;
  padding: 10px 20px;
  background-color: #dc3044;
}
.info-name {
  font-size: 20px;
  color: #fff;
}
.info-targets-wrapper {
  font-size: 12px;
  color: #eee;
  margin-top: 5px;
}
.info-targets {
  font-size: 16px;
  color: #fff;
  padding: 0 5px;
}

.info-right {
  display: flex;
  align-items: center;
  height: 60px;
}
.img-msg-wrapper {
  width: 30px;
  height: 30px;
  margin-right: 15px;
}
.img-portrait-wrapper {
  width: 50px;
  height: 50px;
}

.scroll-view-position {
  height: 100px;
  background-color: #dc3044;
  border-bottom-left-radius: 20px;
  border-bottom-right-radius: 20px;
  padding: 0px 20px;
  position: relative;
}

.scroll-view_h {
  white-space: nowrap;
  position: absolute;
  top: 35px;
}
.scroll-text {
  font-size: 16px;
  color: #fff;
}
.scroll-view {
  display: inline-block;
  background: coral;
  width: 300px;
  height: 100px;
  margin-right: 20px;
}
</style>
