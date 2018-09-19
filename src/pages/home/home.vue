<template>
  <div class="home">
    <home-header></home-header>
    <clock></clock>
    <time-table class="table"></time-table>
    <footer></footer>
  </div>
</template>

<script>
import HomeHeader from './components/header'
import Clock from './components/clock'
import TimeTable from './components/timetable'
import Footer from './components/footer'
import $ from 'jquery';
export default {
  name: 'Home',
  components: {
    HomeHeader,
    Clock,
    TimeTable,
    Footer
  }
}
</script>

<style lang="stylus" scoped>
  .home
    background-color: #f5f5f5
    weight: 360px
    height: 640px
    .table
      width: 360px
</style>
