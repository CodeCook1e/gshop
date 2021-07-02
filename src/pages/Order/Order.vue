<template>
  <section class="order">
    <header-top title="订单列表"></header-top>
    <section class="order_no_login">
      <img src="./images/person.png" />
      <div v-if="!userInfo._id">
        <h3>登录后查看外卖订单</h3>
        <router-link to="/login" tag="button">立即登录</router-link>
      </div>
      <div v-else>
        <h3>暂无订单</h3>
      </div>
    </section>
  </section>
</template>

<script>
import HeaderTop from "../../components/HeaderTop/HeaderTop.vue";
import { mapState } from "vuex";
export default {
  components: {
    HeaderTop,
  },
  computed: {
    ...mapState(["userInfo"]),
  },
};
</script>

<style lang="stylus" rel="stylesheet/stylus">
.header
  background-color #02a774
  position fixed
  z-index 100
  left 0
  top 0
  width 100%
  height 45px
  .header_search
    position absolute
    left 15px
    top 50%
    transform translateY(-50%)
    width 10%
    height 50%
    .icon-sousuo
      font-size 25px
      color #fff
  .header_title
    position absolute
    top 50%
    left 50%
    transform translate(-50%, -50%)
    width 50%
    color #fff
    text-align center
    .header_title_text
      font-size 20px
      color #fff
      display block
  .header_login
    font-size 14px
    color #fff
    position absolute
    right 15px
    top 50%
    transform translateY(-50%)
    .header_login_text
      color #fff
.order
  width 100%
  .order_no_login
    padding-top 140px
    width 60%
    margin 0 auto
    text-align center
    >img
      display block
      width 100%
      height 30%
    >div h3
      padding 10px 0
      font-size 17px
      color #6a6a6a
    >div button
      display inline-block
      background #02a774
      font-size 14px
      color #fff
      border 0
      outline none
      border-radius 5px
      padding 10px 20px
</style>