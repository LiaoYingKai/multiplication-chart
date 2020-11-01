<template>
  <div class="app__title">
    <div class="app__title-line"></div>
    <div class="app__title-text">
      <p>九九乘法表</p>
      <p>MULTIPLICATION CHART</p>
    </div>
    <div class="app__title-line"></div>
  </div>
  <template v-for="num in 9" :key="num">
    <MultiplicationChart  :num="num" v-if="num !== 1"/>
  </template>
</template>

<script>
import MultiplicationChart from './components/MultiplicationChart.vue'

export default {
  name: 'App',
  components: {
    MultiplicationChart
  }
}
</script>

<style lang="scss">
html, body {
  margin: 0;
  background-color: #f0f0f0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2EB738;
  padding: 85px 80px;
  display: grid;
  width: 1280px;
  box-sizing: border-box;
  margin: 0 auto;
  grid-template-columns: repeat(3, 1fr);
  grid-column-gap: 30px;
  grid-row-gap: 40px;

  p {
    line-height: 1;
    margin: 0;
  }
}
.app__title {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  &-text {
    > p {
      font-size: 24px;
      &:first-child {
        font-size: 56px;
      }
    }
  }
  &-line {
    width: 280px;
    height: 2px;
    background-color: #2EB738;
    position: relative;
    margin: 20px 0;
    &::before, &::after {
      content: 'x';
      color: #2EB738;
      font-size: 24px;
      position: absolute;
    }
    &::after {
      left: -20px;
      top: -17px;
    }
    &::before {
      right: -20px;
      top: -17px;
    }
  }
}
</style>
