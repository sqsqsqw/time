<template>
  <div class="clockpage">
    <div class="clock-setting-icon">
        <span class="iconfont" :style="{fontSize: 20 + 'px' }">&#xec08;</span>
    </div>
    <center>
      <p id="date"></p>
      <p id="time"></p>
    </center>
    <center>
      <div class="add">
        <div class="addicon">
          <span class="iconfont" :style="{fontSize: 20 + 'px'}">&#xe6df;</span>
        </div>
        <div class="addtext">
          &nbsp;&nbsp;添加事项
        </div>
      </div>
    </center>
  </div>

</template>

<script>

export default {
  name: 'Clock',
  mounted: function () {
    gettime()
  }
}
var time = ''
var date = ''

function gettime () {
  var d = new Date()
  time = d.getHours() + ':' + checkTime(d.getMinutes()) + ':' + checkTime(d.getSeconds())
  date = d.getFullYear() + '-' + d.getMonth() + '-' + d.getDate()
  document.getElementById('time').innerText = time
  document.getElementById('date').innerText = date
  setTimeout(function () { gettime() }, 1000)
}

function checkTime (i) {
  if (i<10) {
    i= '0' + i
  }
  return i
}

</script>

<style lang="stylus" scoped>
  .clockpage
    height: 164px
    background-color: #ededed
    text-align: center
    .clock-setting-icon
      float: right
      padding 15px 15px 0 0
      color: #2a82e4
    #time
      letter-spacing: 0.07em
      font-size: 35px
      padding: 10px 0
    #date
      width: 200px
      letter-spacing: 0.05em
      font-size: 13px
      padding: 25px 0 0 0
    .add
      height: 45px
      width: 330px
      border-radius: 3px
      background: #fafafa
      border: 3px soild #0f0f0f
      margin: 7px 0 0 0
      line-height: 45px
      color: #808080
      .addicon
        padding: 0 0 0 110px
        float: left
        color: #999999
      .addtext
        width: 110px
        line-height: 45px
        color: #808080

</style>
