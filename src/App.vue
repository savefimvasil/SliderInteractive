<!--Пробовал реализовать слайдер при помощи vue и вот что получилось) Изначально планировал реализовать по другому принципу:-->
<!--При нажатии на кнопку анимировать и удалять крайний и затем создавать новый cо случайной картинкой с другой стороны, но потерпел-->
<!--неудачу из-за отсутствия опыта работы с виртуальным DOM и render-function для него во Vue. На работу в том виде, котором она есть сейчас-->
<!--потратил около 9-11 часов + несколько часов для изучения основ sass и около 4 часов пробовал сделать так, как хотел изначально.-->
<template>
  <div id="app">
    <!--вызов компонента слайдера-->
    <slider></slider>
  </div>
</template>

<script>
// Импорт компонента слайдера
import Slider from './components/Slider'
export default {
  components: {
    // Инициализация компонента слайдера
    Slider
  }
}
</script>

<style lang="scss">
  /*Импорт цветов*/
  @import "sass/colors";
  /*подключение шрифта*/
  @font-face {
    font-family: 'NeuronHeavy';
    src: url("fonts/NeuronHeavy.otf") format("opentype");
  }
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
  /*Общие стили для приложения. Указание высоты во всю высоту окна*/
  #app{
    display: -webkit-box;
    display: -moz-box;
    display: -ms-flexbox;
    display: -webkit-flex;
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 0;
    padding: 0;
    height: 100vh;
    background: radial-gradient($lighterBgc, $darkerBgc);
  }
</style>
