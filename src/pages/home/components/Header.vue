<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-center">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题</div>
    <router-link to='/city'>
      <div class="header-right">
        {{this.$store.state.city}}<span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default{
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  .header
    line-height: .86rem
    display: flex
    background: #00bcd4
    color: #fff
    .header-left
      float: left
      width: .64rem
      .back-icon
        font-size: .4rem
        text-align: center
    .header-center
      flex: 1
      height: .64rem
      line-height: .64rem
      padding-left: .1rem
      margin-top: .12rem
      margin-left: .1rem
      background: #fff
      border-radius: .1rem
      color: #ccc
    .header-right
      width: 1.24rem
      float: right
      text-align: center
      color: #eee
      .arrow-icon
        font-size: .2rem
        padding-left: .1rem
</style>
