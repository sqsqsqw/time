<template>
  <div class="home">
    <home-header></home-header>
    <clock></clock>
    <time-table class="table"></time-table>
  </div>
</template>

<script>
import HomeHeader from './components/header'
import Clock from './components/clock'
import TimeTable from './components/timetable'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    Clock,
    TimeTable
  }
}
</script>

<style lang="stylus" scoped>
  .home
    background-color: #f5f5f5
    weight: 360px
    height: 640px
    .table
      width: 375px
</style>
