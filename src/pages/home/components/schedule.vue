<template>
  <div>
    <div class='sch'>
      <div class='sch-add'>
        <div class="sch-add-date">
          <div class="date"><span :style="{fontSize:  1.325 + 'rem'}">{{schDate()}}</span><br>{{schDay()}}</div>
        </div>
        <div class="sch-add-btn">
          点击新建日程
        </div>
      </div>
      <div class="sch-data">

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Schedule',
  mounted() {
  },
  methods: {
    schDate: function() {
      return new Date().getDate()
    },
    schDay: function() {  
      switch(new Date().getDay()){
        case 1: return '周一'
        case 2: return '周二'
        case 3: return '周三'
        case 4: return '周四'
        case 5: return '周五'
        case 6: return '周六'
        case 7: return '周日'
      }
    }
  }
}

</script>

<style lang="stylus" scoped>
  .sch
    background: #f5f5f5
    height: 32.125rem
    width: 22.5rem
    margin: 0
    .sch-add
      background:#ffffff
      border-radius: 0.5rem
      width: 94%
      height: 6.25rem
      margin-left: 3%
      transform:translateY(1rem) 
      .sch-add-date
        line-height: 1.125rem
        transform:translate(7% ,80%) 
        font-size: 0.8125rem
        color: #555555
      .sch-add-btn
        border: 0.0625rem solid #8c8c8c
        border-radius: 0.5rem
        height: 60%
        width: 70%
        transform:translate(33% , -31%) 
        color: #bbbbbb
        line-height: 3.75rem
        text-align:center
        font-size: 0.9375rem
    .sch-data
      background:#ffffff
      border-radius: 0.5rem
      width: 94%
      height: 71%
      margin-left: 3%
      transform:translateY(2rem) 
</style>
