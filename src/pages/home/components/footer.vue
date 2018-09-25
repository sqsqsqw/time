<template>
  <div class='footer'>
    <hr class='border'/>
    <div class='menu'>
      <center>
        <div class='piece'>
          <div class="foot-icon">
            <img src="../static/img/foot-gray-1.png">
          </div>
            <div class="foot-text">安排</div>
        </div>
        <div class='piece'>
          <div class="foot-icon">
            <img src="../static/img/foot-gray-2.png">
          </div>
          <div class="foot-text">统计</div>
        </div>
        <div class='piece'>
          <div class="foot-icon">
            <img src="../static/img/foot-gray-3.png">
          </div>
          <div class="foot-text">发现</div>
        </div>
        <div class='piece'>
          <div class="foot-icon">
            <img src="../static/img/foot-gray-4.png">
          </div>
            <div class="foot-text">我的</div>
        </div>
      </center>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Foot'
}
</script>

<style lang="stylus" scoped>
    .footer
      width: 100%
      height: 100%
      backgroung-color: #156565
      .border
        width: 100%
        margin: 0
        padding: 0
        background-color: #cccccc
        height: 2px
        border: 0px
      .menu
        width: 100%
        height: 100%
        .piece
          width: 25%
          height: 100%
          float: left
          padding-top: 13px
          .foot-text
            font-size: 10px
            color: gray
      
</style>
