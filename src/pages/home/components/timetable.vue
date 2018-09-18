<template>
  <div class="timetable">
    <div id="table" ></div>
  </div>
</template>

<script>
import echarts from 'echarts'
import Vue from 'vue'
Vue.prototype.$echarts = echarts
export default {
  name: 'TimeTable',
  mounted: function () {
    this.draw();
  },
  methods: {
    draw: function () {
      var myChart = echarts.init(document.getElementById('table'));

        // 指定图表的配置项和数据
        var option = {
            tooltip: {},
            toolbox: {
              
            },
          xAxis: {
            data: ["0:00","1:00","2:00","3:00","4:00","5:00","6:00","7:00","8:00","9:00","10:00","11:00","12:00","13:00","14:00","15:00","16:00","17:00","18:00","19:00","20:00","21:00","22:00","23:00","24:00"],
            position: 'top',
            boundaryGap: false,
            axisTick: {
              length: 270
            }
          },
          yAxis: {
            show: false,
          },
          series: [{
              type: 'line'
          }]
        };
        myChart.setOption(option);
    }
  }
}
</script>

<style lang="stylus" scoped>
  .timetable
    width: 375px
    height: 400px
    #table
      width: 2000px
      height: 400px
  
</style>
