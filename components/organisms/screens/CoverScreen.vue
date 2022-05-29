<template>
  <div class="cover-screen">
    <div class="cover-screen__bg-video-container">
      <video class="cover-screen__bg-video" autoplay muted loop>
        <source src="@/assets/videos/background.mp4" type="video/mp4" />
      </video>
    </div>
    <img class="cover-screen__logo" src="@/assets/images/logo.png"/>
    <div class="cover-screen__content">
      <div>
        <div class="cover-screen__federal-container">
          <img class="cover-screen__federal-logo" src="@/assets/images/federal.png"/>
          <p class="cover-screen__federal-subtitle">Присоединяйся и будь в числе лидеров!</p>
        </div>
        <p class="cover-screen__start-at">запуск — 2 ИЮНЯ 20:00 <sup>(мск)</sup></p>
      </div>
      <p class="cover-screen__additional">
        На Федеральном все начинают <MarkedText>с нуля</MarkedText><br>
        Перенос персонажей с других серверов не осуществляется
      </p>
    </div>
    <div class="cover-screen__end">
      <Button>Играть сейчас!</Button>
      <SideBorderedText><MarkedText>бонусы</MarkedText> и подробности <MarkedText>внизу!</MarkedText></SideBorderedText>
      <MouseScrollIcon/>
    </div>
  </div>
</template>

<script>
export default {
  name: "CoverScreen"
}
</script>

<style lang="scss" scoped>
.cover-screen {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;

  height: 100vh;

  box-sizing: border-box;
  padding: 1.5vw;

  //background-image: url("../../../assets/images/bg-1.png");
  //background-size: cover;


  &__bg-video-container {
    position: absolute;
    z-index: -1;

    width: 100%;
    height: 100%;

    left: 0;
    top: 0;
  }
  &__bg-video {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  &__logo {
    height: 5vw;
  }

  &__content {
    display: flex;
    align-items: center;
    gap: 4vw;
  }

  &__federal-container {
    margin-bottom: 1vw;
  }

  &__federal-logo {
    height: 4vw;
  }

  &__federal-subtitle {
    margin-left: 5vw;

    color: white;

    font-size: .8vw;
    font-weight: 600;
  }

  &__start-at {
    color: white;

    font-size: 2vw;
    font-weight: 700;
    text-transform: uppercase;

    sup {
      font-size: 1vw;
    }
  }

  &__additional {
    width: 18vw;
    height: fit-content;

    padding: 1.5vw;

    color: white;

    font-size: .9vw;
    font-weight: 600;
    text-align: center;

    background-color: black;
    border-top: .5vw solid #DD3232;
  }

  &__end {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1vw;
  }
}
</style>
