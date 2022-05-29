<template>
  <div class="bordered-block">
    <p class="bordered-block__title">{{title}}<br></p>
    <div class="bordered-block__border" :style="{opacity: Number(!hideBorder)}"/>
    <div class="bordered-block__body">
      <slot/>
    </div>
  </div>
</template>

<script>
export default {
  name: "BorderedBlock",
  props: {
    title: String,
    align: String,
    hideBorder: Boolean
  }
}
</script>

<style lang="scss" scoped>
.bordered-block {

  &__title {
    color: white;

    font-weight: 700;
    font-size: .9vw;
    text-transform: uppercase;
  }
  &__border {
    width: 75%;
    max-width: 15vw;
    height: .5vw;

    background-color: #DD3232;

    transform: translateY(50%);
  }
  &__body {
    padding: 1vw;

    background-color: #313844;
  }
}
</style>
