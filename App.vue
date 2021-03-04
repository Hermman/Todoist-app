<script>
export default {
  onLaunch: function () {
    console.log("App Launch");
    uni.onTabBarMidButtonTap(() => {
      console.log("添加代办");
    });
  },
  onShow: function () {
    console.log("App Show");
  },
  onHide: function () {
    console.log("App Hide");
  },
};
</script>

<style>
/*每个页面公共css */
:root {
  --themeColor: "#DC3044";
  --themeBackgroundColor: "";
}
</style>
