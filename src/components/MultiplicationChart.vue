<template>
  <div class="multiplication-chart">
    <div>
      <div class="multiplication-chart__title">
        {{num}}
      </div>
      <div v-for="item in oneToThree" :key="item" class="multiplication-chart__formula">
        {{num}} x {{item}} = {{num * item}}
      </div>
    </div>
    <div>
      <div v-for="item in fourToNine" :key="item" class="multiplication-chart__formula">
        {{num}} x {{item}} = {{num * item}}
      </div>
    </div>
    
  </div>
</template>

<script>
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'MultiplicationChart',
  props: {
    num: Number
  },
  setup() {
    const oneToThree = [1,2,3]
    const fourToNine = [4,5,6,7,8,9]
    
    return {
      oneToThree,
      fourToNine
    }
  }
})
</script>

<style scoped lang="scss">
.multiplication-chart {
  padding: 60px 40px;
  box-sizing: border-box;
  width: 350px;
  height: 366px;
  border-radius: 100px 0px 30px 0px;
  background: #FFFFFF;
  box-shadow: 0px 3px 10px #D8D8D8;
  display: flex;
  justify-content: space-between;
  font-family: sans-serif;
  &__title {
    text-align: left;
    font-size: 128px;
    font-weight: bold;
    text-shadow: 4px 3px 0px #F0F0F0;
    line-height: 123px;
    text-align: center;
  }
  &__formula {
    font-size: 24px;
    text-align: left;
    margin-bottom: 8px;
    height: 33px;
  }
}
</style>
