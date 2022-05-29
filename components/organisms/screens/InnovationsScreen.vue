<template>
  <div class="innovations-screen">
    <h2 class="innovations-screen__title">марафон испытаний</h2>
    <div class="innovations-screen__description">
      <p class="innovations-screen__description-section innovations-screen__description-section_left">
        <span>
          Первые <MarkedText>2 недели</MarkedText> от старта сервера<br>
          будут идти специальные испытания
        </span>
      </p>
      <img class="innovations-screen__description-arrow" src="@/assets/images/arrow.svg"/>
      <p class="innovations-screen__description-section innovations-screen__description-section_right">
        <span>
          Прими в них участие и получи<br>
          <MarkedText>награды</MarkedText>
          по окончанию марафона!
        </span>
      </p>
    </div>
    <div class="innovations-screen__slider-container">
      <Slider :contentLength="2" @next="onSliderNext" @previous="onSliderPrevious">
        <template v-slot="{currentContentIndex}">
          <transition-group :name="currentTransition" tag="div" class="innovations-screen__slider-content">
            <div :key="1" class="innovations-screen__slide" v-if="currentContentIndex === 0">
              <BorderedBlock class="reward-block" title="картельные войны">
                <div class="reward-block__content">
                  <p class="reward-block__title">победители в битве за картель</p>
                  <ul>
                    <li class="reward-block__text">
                      <span class="reward-block__text_marked">500</span> рублей на игровой кошелек<br>
                      каждому игроку в клане<br>
                      + <span class="reward-block__text_marked">200</span> оружейных инструментов<br>
                      + <span class="reward-block__text_marked">10</span> инструментов сейва оружия<br>
                    </li>
                  </ul>
                </div>
              </BorderedBlock>
              <BorderedBlock class="reward-block" title="Первые по имуществу">
                <div class="reward-block__content">
                  <ul>
                    <li class="reward-block__text">
                      1 место: <span class="reward-block__text_marked">5x</span> кейс Сотка
                    </li>
                    <li class="reward-block__text">
                      2 место: <span class="reward-block__text_marked">3x</span> кейс Сотка
                    </li>
                    <li class="reward-block__text">
                      3 место: <span class="reward-block__text_marked">2x</span> кейс Сотка
                    </li>
                  </ul>
                </div>
              </BorderedBlock>
              <BorderedBlock class="reward-block" title="Первый лидер">
                <div class="reward-block__content">
                  <p class="reward-block__title">Первый лидер на посту</p>
                  <p class="reward-block__subtitle">без выговоров за время ивента</p>
                  <ul>
                    <li class="reward-block__text">
                      <span class="reward-block__text_marked">3к</span> рублей на игровой кошелек<br>
                      + <span class="reward-block__text_marked">1</span> кейс сотка<br>
                      + <span class="reward-block__text_marked">10</span> дорогих кейсов жетонов<br>
                    </li>
                  </ul>
                  <p class="reward-block__additional-text">Распространяется на все фракции</p>
                </div>
              </BorderedBlock>
              <img class="innovations-screen__slide-gold-1" src="@/assets/images/gold.png"/>
              <img class="innovations-screen__slide-case" src="@/assets/images/100-preview.png"/>
            </div>
            <div :key="2" class="innovations-screen__slide" v-if="currentContentIndex === 1">
              <BorderedBlock class="reward-block" title="по уровню">
                <div class="reward-block__content">
                  <p class="reward-block__title">Топовые игроки</p>
                  <ul>
                    <li class="reward-block__text">
                      ТОП 1: <span class="reward-block__text_marked">10к</span> рублей на игровой кошелек<br>
                      + <span class="reward-block__text_marked">5х</span> кейс сотка
                    </li>
                    <li class="reward-block__text">
                      ТОП 1: <span class="reward-block__text_marked">10к</span> рублей на игровой кошелек<br>
                      + <span class="reward-block__text_marked">2х</span> кейс сотка
                    </li>
                    <li class="reward-block__text">
                      ТОП 3: <span class="reward-block__text_marked">5к</span> рублей на игровой кошелек<br>
                      + <span class="reward-block__text_marked">2х</span> кейс сотка
                    </li>
                  </ul>
                </div>
              </BorderedBlock>
              <BorderedBlock class="reward-block" hide-border>
                <div class="reward-block__content">
                  <p class="reward-block__title">Все игроки дошедшие до:</p>
                  <ul>
                    <li class="reward-block__text">
                      15 уровня: <span class="reward-block__text_marked">500</span> рублей на игровой кошелек<br>
                      + <span class="reward-block__text_marked">10</span> обычных кейсов с жетонами
                    </li>
                    <li class="reward-block__text">
                      20 уровня: <span class="reward-block__text_marked">1к</span> рублей на игровой кошелек<br>
                      + <span class="reward-block__text_marked">5</span> дорогих кейсов с жетонами <br>
                      + <span class="reward-block__text_marked">10</span> обычных кейсов с жетонами <br>
                    </li>
                    <li class="reward-block__text">
                      25 уровня: <span class="reward-block__text_marked">2к</span> рублей на игровой кошелек<br>
                      + <span class="reward-block__text_marked">10</span> дорогих кейсов с жетонами <br>
                      + <span class="reward-block__text_marked">10</span> обычных кейсов с жетонами <br>
                    </li>
                  </ul>
                </div>
              </BorderedBlock>
              <img class="innovations-screen__slide-gold-2" src="@/assets/images/gold.png"/>
              <img class="innovations-screen__slide-tokens" src="@/assets/images/tokens.png"/>
            </div>
          </transition-group>
        </template>
      </Slider>

    </div>
    <Button>Играть сейчас!</Button>
  </div>
</template>

<script>
export default {
  name: "InnovationsScreen",
  data: function () {
    return {
      currentTransition: ""
    }
  },
  methods: {
    onSliderNext: function () {
      this.currentTransition = 'slide-right';
    },
    onSliderPrevious: function () {
      this.currentTransition = 'slide-left';
    }
  }
}
</script>

<style lang="scss" scoped>
.innovations-screen {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;

  height: 100vh;

  box-sizing: border-box;
  padding: 2vw 1.5vw;

  background-image: url("../../../assets/images/bg-2.png");
  background-size: cover;
  background-position: top center;

  overflow: hidden;

  &__title {
    color: white;

    font-size: 1.5vw;
    font-weight: 700;
    text-transform: uppercase;
  }

  &__description {
    display: flex;

    margin-bottom: 2vw;
  }

  &__description-section {
    display: flex;
    align-items: center;
    justify-content: center;

    height: 5vw;

    box-sizing: border-box;
    padding: 1vw;
    margin-top: .72vw;

    color: white;

    font-size: .8vw;
    font-weight: 700;

    background: #313844;

    &_left {
      border-left: .5vw solid #DD3232;
    }

    &_right {
      border-right: .5vw solid #DD3232;
    }
  }

  &__description-arrow {
    height: 6.2vw;

    margin-top: .1vw;
  }

  &__slider-content {
    height: 25vw;
    width: 60vw;

    position: relative;
  }

  &__slide {
    display: flex;
    justify-content: center;
    gap: 1vw;

    width: 100%;

    position: absolute;
  }

  &__slide-gold-1 {
    position: absolute;
    left: -10vw;
    bottom: -5vw;

    height: 15vw;
  }

  &__slide-case {
    position: absolute;
    left: 30vw;
    bottom: -6vw;


    height: 13vw;
  }

  &__slide-gold-2 {
    position: absolute;
    left: -5vw;
    bottom: -5vw;

    height: 15vw;
  }

  &__slide-tokens {
    position: absolute;
    left: 25vw;
    bottom: -6.5vw;

    height: 9vw;
  }
}

.reward-block {

  &__content {
    height: 15vw;

    box-sizing: border-box;
    padding: 1vw 1.5vw;
  }

  &__title {
    color: white;

    font-weight: 600;
    font-size: .9vw;
    text-align: center;
    text-transform: uppercase;
  }

  &__subtitle {
    color: white;

    font-weight: 600;
    font-size: .8vw;
    text-align: center;
  }

  &__text {
    margin-top: 1vw;

    color: white;

    font-weight: 600;
    font-size: .8vw;

    &_marked {
      color: #FFD771;

      font-weight: 700;
    }
  }

  &__additional-text {
    margin-top: 1vw;

    color: white;

    font-weight: 400;
    font-size: .75vw;
  }
}

</style>
