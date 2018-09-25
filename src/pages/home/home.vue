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
import Swiper from 'swiper'
import $ from 'jquery'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    Clock,
    TimeTable,
    Foot
  },
  mounted: function () {
    this.swip2init();
  },
  methods: {
    swip2init: function() {
      var myswiper = new Swiper('#swiper1');
    }
  }
}
</script>

<style lang="stylus" scoped>
  .home
    background-color: #f5f5f5
    weight: 360px
    height: 640px
    .head
      width: 360px
      height: 60px
    .content
      width: 360px
      height: auto
    .foot
      width: 360px
      height: 64px
</style>
