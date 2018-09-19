<template>
  <div class="timetable">
    <div class="swiper-container">
      <div class="swiper-wrapper">
        <div class="swiper-slide">
          <div id="table" ></div>
        </div>
        <div class="swiper-slide">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import echarts from 'echarts'
import Vue from 'vue'
import Swiper from 'swiper'
Vue.prototype.$echarts = echarts
export default {
  name: 'TimeTable',
  mounted: function () {
    this.drawlines();
    this.swip();
  },
  methods: {
    drawlines: function () {
      var myChart = echarts.init(document.getElementById('table'));

        // 指定图表的配置项和数据
        var option = {
          tooltip: {},
          xAxis: {
            data: ["0:00","1:00","2:00","3:00","4:00","5:00","6:00","7:00","8:00","9:00","10:00","11:00","12:00","13:00","14:00","15:00","16:00","17:00","18:00","19:00","20:00","21:00","22:00","23:00","24:00"],
            position: 'top',
            boundaryGap: false,
            axisTick: {
              length: 270
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
    swip: function(){
       var swiper = new Swiper('.swiper-container', {
        freeMode: true
      });
    }
  }
}


</script>

<style lang="stylus" scoped>
  .timetable
    width: 360
    height: 400px
    overflow-x: hidden
    .swiper-container
      width: 2800px
      height: 100%
      .swiper-slide
        margin-left: -170px
        width: 2000px
        float: left
    #table
      width: 3500px
      height: 400px
      padding: 0
      margin: 0
  
</style>
