<template>
  <div class="slider-item-container">
    <div class="slider-item">
      <!--байндим путь к картинке-->
      <img :src="imgPathComp">
    </div>
  </div>
</template>

<script>
export default {
  props: ['slide'],
  computed: {
    imgPathComp: function () {
      // рандомная генерация картинки
      return require('../img/boy' + (Math.floor(Math.random() * (2)) + 1) + '.png')
    }
  }
}
</script>

<style lang="scss" scoped>
  @import "../sass/colors";
  /*Общие стили для внешнего блока слайдера*/
  .slider-item-container{
    height: 200px;
    width: 200px;
    margin: 70px 30px;
    display: -webkit-box;
    display: -moz-box;
    display: -ms-flexbox;
    display: -webkit-flex;
    display: flex;
    align-items: flex-end;
    border: 5px solid $borderUnDirect;
    border-radius: 50%;
    transition: 0.3s ease;
    &:hover{
      border-color: white;
      box-shadow: 0 10px 10px -5px rgba(1,1,1,0.4);
      transition: 0.3s ease;
      img{
        animation-name: jumpAnimation;
        animation-duration: 0.3s;
        transform: translateY(15px);
        transition: 0.3s ease;
      }
    }
    /*Анимация выпрыгивания персонажа*/
    @keyframes jumpAnimation {
      0%  {transform: translateY(20px)}
      15% {transform: translateY(17.5px)}
      30% {transform: translateY(15px)}
      45% {transform: translateY(12.5px)}
      60% {transform: translateY(10px)}
      75% {transform: translateY(12.5px)}
      100%{transform: translateY(15px)}
    }
  }
  /*Стили для картинки и внутреннего блока единицы слайдера*/
  .slider-item{
    display: flex;
    display: -webkit-box;
    display: -moz-box;
    display: -ms-flexbox;
    display: -webkit-flex;
    clip-path: inset(-100% 0 0 round 50%);
    justify-content: center;
    align-items: flex-end;
    width: 200px;
    height: 200px;
    img{
      height: 265px;
      transform: translateY(20px);
      transition: 0.3s ease;
    }
  }
</style>
