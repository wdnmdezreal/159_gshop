<template>
  <div class="footer_guide" v-show="$route.meta.showFooter">
    <span
      class="guide_item"
      :class="{ on: '/msite' === $route.path }"
      @click="goTo('/msite')"
    >
      <span class="item_icon">
        <i class="iconfont icon-shopwaimaihe"></i>
      </span>
      <span>外卖</span>
    </span>
    <a
      href="javascript:;"
      class="guide_item"
      :class="{ on: '/search' === $route.path }"
      @click="goTo('/search')"
    >
      <span class="item_icon">
        <i class="iconfont icon-shopsearch"></i>
      </span>
      <span>搜索</span>
    </a>
    <a
      href="javascript:;"
      class="guide_item"
      :class="{ on: '/order' === $route.path }"
      @click="goTo('/order')"
    >
      <span class="item_icon">
        <i class="iconfont icon-shopdingdan"></i>
      </span>
      <span>订单</span>
    </a>
    <a
      href="javascript:;"
      class="guide_item"
      :class="{ on: '/profile' === $route.path }"
      @click="goTo('/profile')"
    >
      <span class="item_icon">
        <i class="iconfont icon-shopgeren"></i>
      </span>
      <span>我的</span>
    </a>
  </div>
</template>

<script>
export default {
  name: "FooterGuide",
  methods: {
    goTo(path) {
      // ```replace```是替换当前记录
      this.$router.replace(path);
    },
  },
};
</script>

<style lang="stylus">
@import '../../common/stylus/mixins.styl';

.footer_guide { // footer
  top-border-1px(#e4e4e4);
  position: fixed;
  z-index: 100;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #fff;
  width: 100%;
  height: 50px;
  display: flex;

  a {
    text-decoration: none;
  }

  .guide_item {
    display: flex;
    flex: 1;
    text-align: center;
    flex-direction: column;
    align-items: center;
    margin: 5px;
    color: #999999;

    &.on {
      color: #02a774;
    }

    span {
      font-size: 12px;
      margin-top: 2px;
      margin-bottom: 2px;

      .iconfont {
        font-size: 22px;
      }
    }
  }
}
</style>