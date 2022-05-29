<template>
  <div class="bonus-screen">
    <div class="bonus-screen__section">
      <h2 class="bonus-screen__title">Бонусы для всех игроков</h2>
      <p class="bonus-screen__subtitle">Врывайся в игру прямо сейчас и получай вкусные ништяки!</p>
      <hr class="bonus-screen__divider"/>
      <img class="bonus-screen__crown" src="@/assets/images/crown.png"/>
      <p class="bonus-screen__name">Премиум аккаунт на 14 дней!</p>
      <p class="bonus-screen__enter-promo">вводи ПРОМОКОД</p>
      <p class="bonus-screen__promo">FEDERAL</p>
      <HowToUsePromo/>
    </div>
    <Button>Играть сейчас!</Button>

  </div>
</template>

<script>
export default {
  name: "BonusScreen"
}
</script>

<style lang="scss" scoped>
.bonus-screen {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;

  height: 100vh;

  box-sizing: border-box;
  padding: 5vw 1.5vw;

  background-image: linear-gradient(transparent 0%, transparent 80%, black 100%), url("../../../assets/images/bg-3.png");
  background-size: cover;
  background-position: top center;

  &__section {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &__title {
    margin-bottom: 1vw;

    color: white;

    font-size: 1.5vw;
    font-weight: 700;
    text-transform: uppercase;
  }

  &__subtitle {
    margin-bottom: 1vw;

    color: white;

    font-size: .9vw;
    font-weight: 700;
  }

  &__divider {
    margin-bottom: 2vw;

    width: 14vw;
  }

  &__crown {
    margin-bottom: 1vw;

    width: 6vw;
  }

  &__name {
    margin-bottom: 1.5vw;

    color: white;

    font-size: .9vw;
    font-weight: 700;
    text-transform: uppercase;
  }

  &__enter-promo {
    margin-bottom: .5vw;

    color: white;

    font-size: .9vw;
    font-weight: 600;
    text-transform: uppercase;
  }

  &__promo {
    margin-bottom: 1vw;
    padding: .2vw .6vw;

    color: white;

    font-size: 1.5vw;
    font-weight: 600;

    border: .15vw dashed #DD3232;
  }
}
</style>
