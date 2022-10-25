<script setup>

</script>
<template>
  <div class="box">
    <div class="main ">
      <div class="item box-1">
        <div class="text">
          <p >写五个字哦123个</p>
          <p >写五个字哦123个</p>
        </div>
        <svg class="icon-yun" aria-hidden="true">
          <use xlink:href="#icon-a-tupianyihuifu-58"></use>
        </svg>
      </div>
    </div>
    <div class="main box-2">
      <div class="item">
        <div class="info">
          <div class="text">
            <p >写五个字哦123个</p>
            <p >写五个字哦123个</p>
          </div>
          <svg class=" icon-yun" aria-hidden="true">
            <use xlink:href="#icon-a-tupianyihuifu-58">
            </use>
          </svg>
        </div>
      </div>
    </div>
    <div class="main box-3">
      <div class="item">
        <div class="info">
          <div class="text">
            <p >写五个字哦123个</p>
            <p >写五个字哦123个</p>
          </div>
          <svg class=" icon-yun" aria-hidden="true">
            <use xlink:href="#icon-a-tupianyihuifu-58">
            </use>
          </svg>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
body {
  background: #333;
}

.box {
  display: flex;
  justify-items: center;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  transform: translate(0, -15px);
}

.main {
  width: 350px;
  height: 350px;
  //background: #333;
  //opacity: 0.5;
  border-radius: 50%;
  position: absolute;
  z-index: 10;
  //border: 1px solid #333;
  display: flex;
  justify-content: space-around;


  .item {
    width: 175px;
    height: 175px;
    position: absolute;
    top: 0;
    left: 50%;
    transform: translate(-50%);
    z-index: 999;

    .text {
      color: #ffffff;
      position: absolute;
      z-index: 2000;
      display: flex;
      justify-content: center;
      flex-direction: column;
      align-items: center;
      left: 35px;

      p{
        font-size: 12px;
        line-height: 14px;
        margin: 0;
      }
    }
  }


}

.box-1,.box-2,.box-3{
  svg{
    position: absolute;
    top: -75px;
    left: -15px;
    width: 200px;
    height: 150px;
    z-index: 1999;
  }
}

.box-1 {
  transform: rotate(0deg);
}

.box-2 {
  transform: rotate(120deg);
  .info{
    transform: rotate(-120deg);
  }
}

.box-3 {
  transform: rotate(240deg);
  .info{
    transform: rotate(-240deg);
  }
}


</style>
