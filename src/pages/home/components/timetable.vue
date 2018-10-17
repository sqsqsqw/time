<template>
  <div class='timetable'>
    <div class='swiper-container' id='swiper1'>
      <div class='swiper-wrapper'>
        <div class='swiper-slide'>
          <div class="tablebtns">
            <div class='tablebtn' v-for="item in btn">
            <!--  <div class="btn btn-"+{{item.color}} :style="{ width:  {{item.end}}-{{item.start}} + 'px',marginLeft: + {{item.start}} + 450 + 'px',marginTop: 60 + 'px'}">{{item.title}}</div>-->
            </div>
          </div>
          <div class="timeline" :style="{marginLeft: now + 450 + 'px'}"></div>
          <div id='table' ></div>
        </div>
        <div class='swiper-slide'>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import echarts from 'echarts'
import Vue from 'vue'
import Swiper from 'swiper'
import $ from 'jquery'
import 'swiper/dist/css/swiper.css'
var now;
Vue.prototype.$echarts = echarts
export default {
  name: 'TimeTable',
  data () {
    return {
      btn: [{
        id: '0',
        color: 'red',
        title: '吃早饭',
        start: '700',
        end: '740'
      },
      {
        id: '1',
        color: 'green',
        title: '上课',
        start: '800',
        end: '1000'
      }],
      now: now,
      onbtn: ''
    }
  },
  mounted: function () {
    this.drawlines();
    this.swip1init();
  },
  methods: {
    drawlines: function () {
      var myChart = echarts.init(document.getElementById('table'));
      var option = {
        xAxis: {
            data: ['0:00', '1:00', '2:00', '3:00', '4:00', '5:00', '6:00', '7:00', '8:00', '9:00', '10:00', '11:00', '12:00', '13:00', '14:00', '15:00', '16:00', '17:00', '18:00', '19:00', '20:00', '21:00', '22:00', '23:00', '24:00'],
          position: 'top',
          offset: 15,
          boundaryGap: false,
          axisTick: {
            length: 300
          },
          axisLine: {
            lineStyle: {
             color: '#aaa'
            },
          }
        },
          yAxis: {
            show: false

          },
          series: [{
              type: 'line'
          }]
        };
        myChart.setOption(option);
    },
    swip1init: function() {
      var myswiper = new Swiper('#swiper1', {
        freeMode: true,
        on: {
          init: function() {
            this.setTranslate(-now);
            this.emit('transitionEnd');
          }
        }
      });
    }
  }
}
function timeinit() {
  now = new Date();
  now = (now.getHours()*100+(now.getMinutes()/3)*5) * 1.5;
}
window.onload = timeinit();
</script>

<style lang="stylus" scoped>
  .timetable
    height: 350px
    overflow-x: hidden
    background-color: #f4f4f4
    .swiper-container
      width: 3600px
      height: 100%
      .swiper-slide
        margin-left: -270px
        width: 2000px
        float: left
        .btn
          line-height: 50px
          text-align: center
          color: white
          border-radius: 5px
          height: 50px
          position: absolute
          color: white
        .btn-red
          background-color: #ff5454
        .btn-orange
          background-color: #ff9a33
        .btn-yellow
          background-color: #ffce4c
        .btn-green
          background-color: #43cf7c
        .btn-cyan
          background-color: #49cbd0
        .btn-blue
          background-color: #2a82e4
        .btn-purpeo
          background-color: #7948ea
        .btn-gray
          background-color: #808080
        
        .timeline
          width: 2px
          height: 500px
          background-color: red
          position: absolute
        #table
          width: 4500px
          height: 400px
          padding: 0
          margin: 0
  
</style>
