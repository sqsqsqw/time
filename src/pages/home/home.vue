<template>
  <div class='home'>
    <home-header class='head'></home-header>
    <div class='content'>
      <div class='swiper-container' id='swiper2'>
        <div class='swiper-wrapper'>
          <div class='swiper-slide'>
            <clock></clock>
            <time-table class="table"></time-table>
          </div>
          <div class='swiper-slide'>
            <schedule></schedule>
          </div>
          <div class='swiper-slide'>
            <find></find>
          </div>
        </div>
      </div>
    </div>
    <foot class='foot'></foot>
  </div>
</template>

<script>
import HomeHeader from './components/header'
import Clock from './components/clock'
import TimeTable from './components/timetable'
import Foot from './components/footer'
import Schedule from './components/schedule'
import Find from './components/find'
import Swiper from 'swiper'
import 'swiper/dist/css/swiper.css'
import $ from 'jquery'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    Clock,
    TimeTable,
    Foot,
    Schedule,
    Find
  },
  mounted: function () {
    this.swip2init()
    this.getHomeInfo()
  },
  methods: {
    swip2init: function() {
      var myswiper1 = new Swiper('#swiper1')
      var myswiper2 = new Swiper('#swiper2',{
        height: 514,
        width: 360
      })
    },
    getHomeInfo: function() {
      axios.get('/static/moke/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc: function(res){
      console.log(res)
    }
  }
}
</script>

<style lang="stylus" scoped>
  .home
    background-color: #f5f5f5
    weight: 22.5rem
    height: 40rem
    .head
      width: 22.5rem
      height: 3.75rem
    .content
      width: auto
      height: auto
      .swiper-slide
        height: 32.125rem
        width: 22.5rem
    .foot
      width: 22.5rem
      height: 4rem
</style>
