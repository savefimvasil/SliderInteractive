<template>
    <div class="slider">
      <button @click="goToPrev()"><i class="fa fa-chevron-left"></i>НАЗАД</button>
        <div class="slider-items">
          <div class="translation" ref="translation">
            <slider-item :key="i" v-for="(slide, i) in slides"></slider-item>
          </div>
        </div>
      <button @click="goToNext()">ДАЛІ<i class="fa fa-chevron-right"></i></button>
    </div>
</template>

<script>
import SliderItem from './SliderItem'
export default {
  components: {
    SliderItem
  },
  data () {
    return {
      slides: 10,
      currentIndex: 5
    }
  },
  methods: {
    goToPrev () {
      console.log(this.currentIndex)
      this.currentIndex++
      this.currentIndex %= (this.slides - 2)
      this.$refs.translation.style.left = -(270 * this.currentIndex) + 'px'
      console.log(this.currentIndex)
    },
    goToNext () {
      console.log(this.currentIndex)
      if (this.currentIndex <= 0) {
        this.currentIndex = this.slides - 2
      }
      this.currentIndex--
      this.currentIndex %= (this.slides - 2)
      this.$refs.translation.style.left = -(270 * this.currentIndex) + 'px'
      console.log(this.currentIndex)
    }
  },
  mounted () {
    this.$refs.translation.style.left = -(270 * this.currentIndex) + 'px'
  }
}
</script>

<style lang="scss" scoped>
  .translation{
    display: block;
    position: relative;
    transition: left 0.6s ease-out;
  }
  @import "../sass/colors";
  .slider {
    overflow: hidden;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 50px;
    width: 100%;
    .slider-items{
      overflow: hidden;
      transition: left 0.6s ease-out;
      width: 810px;
    }
    div {
      display: flex;
    }
    button {
      font-weight: bold;
      background: none;
      color: white;
      border: 2px solid white;
      border-radius: 5px;
      width: 150px;
      padding: 15px 0;
      font-size: 24px;
      &:first-child {
        transform: perspective(20em) rotateY(30deg);
      }
      &:last-child {
        transform: perspective(20em) rotateY(-30deg);
      }
      &:hover {
        background: white;
        color: $darkerBgc;
        transition: 0.3s
      }
      &:focus{
        outline: none;
      }
    }
  }
</style>
