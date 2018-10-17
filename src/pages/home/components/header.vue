<template>
  <div>
    <div class="header">
      <div class="header-left">
        <span class="iconfont " :style="{fontSize: 20 + 'px'}">&#xe622;</span>
      </div>
      时间戳
      <div class="header-right">
        <span class="iconfont" :style="{fontSize: 20 + 'px'}">&#xe64b;</span>
      </div>
    </div>
    <hr class='border'/>
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
    height: 3.625rem
    line-height: 3.625rem
    background: $bgcolor
    text-align: center
    color: #505050
    .header-left
      height: 1.5rem
      margin-left: 1rem
      float: left
      color: #2a82e4
    .header-right
      height: 1.5rem
      margin-right: 1rem
      float: right
      color: #2a82e4
  
  .border
    width: 100%
    margin: 0
    padding: 0
    background-color: #cccccc
    height: .125rem
    border: 0px
</style>
