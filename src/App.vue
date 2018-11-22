<template>
  <div id="app">
    <slider></slider>
  </div>
</template>

<script>
import Slider from './components/Slider'
export default {
  components: {
    Slider
  }
}
</script>

<style lang="scss">
  @font-face {
    font-family: 'NeuronHeavy';
    src: url("fonts/NeuronHeavy.otf") format("opentype");
  }
  @import "sass/colors";
  *{
    font-family: 'NeuronHeavy', sans-serif;
    font-stretch: ultra-expanded;
    letter-spacing: 2px;
    padding: 0;
    margin: 0;
  }
  .fa{
    margin: 0;
    padding: 0 8px;
    font-size: 18px;
  }
  #app{
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 0;
    padding: 0;
    height: 100vh;
    background: radial-gradient($lighterBgc, $darkerBgc);
  }
</style>
