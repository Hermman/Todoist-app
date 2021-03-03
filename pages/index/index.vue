<template>
  <view class="container">
    <view class="header">
      <text class="header-text">{{ title }}</text>
      <view class="header-search">
        <input class="header-search-input" placeholder="Search Task" />
        <view class="search-icon-wrapper">
          <image class="search-icon" src="/static/image/search.png" />
        </view>
      </view>
      <!-- date list -->
      <view class="header-list-wrapper">
        <view
          class="header-list-item"
          v-for="(item, index) in dateList"
          :key="index"
          @click="handleItem(index)"
        >
          {{ item }}
        </view>
      </view>
    </view>
    <!-- today task -->
    <view class="list-wrapper">
      <text class="list-title">{{ listTitle }}</text>
      <view class="list">
        <view class="list-item" v-for="(item, index) in todoList" :key="index">
          <radio class="list-item-radio" />
          <view>
            <view class="list-item-title">{{ item.title }}</view>
            <view class="list-item-date">{{ item.date }}</view>
          </view>
        </view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      title: "Welcome Back",
      dateList: [10, 11, 12, 13],
      listTitle: "Today Task",
      todoList: [
        { date: new Date().toLocaleDateString(), title: "todo list 1" },
        { date: new Date().toLocaleDateString(), title: "todo list 2" },
        { date: new Date().toLocaleDateString(), title: "todo list 3" },
        { date: new Date().toLocaleDateString(), title: "todo list 4" },
        { date: new Date().toLocaleDateString(), title: "todo list 5" },
      ],
    };
  },
  onLoad() {},
  methods: {
    handleItem(index) {
      console.log(index);
    },
  },
};
</script>

<style>
.container {
  background-color: #fafafa;
}
.header {
  height: 200px;
  padding: 10px;
  background-color: #4264ec;
  border-bottom-left-radius: 20px;
  border-bottom-right-radius: 20px;
}
.header-text {
  font-size: 20px;
  color: #fff;
}
.header-search {
  margin: 10px 15px;
  background-color: #2b49c3;
  border-radius: 10px;
  position: relative;
}
.header-search-input {
  height: 40px;
  line-height: 40px;
  padding-right: 40px;
  text-indent: 10px;
  color: #fff;
}
.search-icon-wrapper {
  width: 24px;
  height: 24px;
  position: absolute;
  top: 10px;
  right: 8px;
}
.search-icon {
  max-width: 100%;
  max-height: 100%;
}

/* date list */
.header-list-wrapper {
  height: 80px;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.header-list-item {
  width: 50px;
  height: 50px;
  line-height: 50px;
  color: #fff;
  font-size: 16px;
  border: 1px solid #fff;
  border-radius: 5px;
  text-align: center;
}
.header-list-item:nth-child(1) {
  background-color: #fd9f30;
  border: 1px solid #fd9f30;
}

/* today task */
.list-wrapper {
  padding: 15px 20px;
}
.list-title {
  font-size: 16px;
  color: #333;
  font-weight: 700;
}
.list-item {
  display: flex;
  align-items: center;
  height: 50px;
  background-color: #fff;
  border-radius: 10px;
  padding: 10px;
  margin: 10px 0;
}
.list-item-radio {
  margin: 0 10px;
}
.list-item-date {
  font-size: 14px;
  color: #ccc;
  margin-top: 5px;
}
.list-item-title {
  font-size: 16px;
  color: #333;
  font-weight: 700;
}
</style>
