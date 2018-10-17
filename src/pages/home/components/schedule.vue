<template>
  <div>
    <div class='sch'>
      <div class='sch-add'>
        <div class="sch-add-date">
          <div class="date">{{schDate()}}<br>{{schDay()}}</div>
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
    height: 514px
    width: 360px
    margin: 0
    .sch-add
      background:#ffffff
      border-radius: 8px
      width: 94%
      height: 100px
      margin-left: 3%
      transform:translateY(20px) 
      .sch-add-date
        line-height: 18px
        transform:translate(5% ,80%) 
        font-size: 13px
        .date
          color: #555555
        .day
          color: #555555
      .sch-add-btn
        border: 1px solid #8c8c8c
        border-radius: 5px
        height: 60%
        width: 70%
        transform:translate(33% , -25%) 
        color: #bbbbbb
        line-height: 60px
        text-align:center
        font-size: 15px
</style>
