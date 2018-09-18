<template>
  <div>
    <div class="header">
      <div class="header-left">
        <img src="../static/img/notice.png">
      </div>
      时间戳
      <div class="header-right">
        <img src="../static/img/setting.png">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header
    height: 60px
    line-height: 60px
    background: $bgcolor
    text-align: center
    color: #505050
    .header-left
      height: 24px
      margin-left: 16px
      margin-top: 10px
      float: left
    .header-right
      height: 24px
      margin-right: 16px
      margin-top: 10px
      float: right
</style>
