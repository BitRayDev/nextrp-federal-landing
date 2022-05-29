<template>
  <div class="home-page">
    <CoverScreen/>
    <InnovationsScreen/>
    <BonusScreen/>
    <Footer/>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style lang="scss">
body {
  &::-webkit-scrollbar {
    width: .5vw;
  }
  &::-webkit-scrollbar-track {
    background-color: black;
  }
  &::-webkit-scrollbar-thumb {
    background-color: #dd3232;
  }
}
</style>
