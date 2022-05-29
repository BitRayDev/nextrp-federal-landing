<template>
  <span class="marked-text">
    <slot/>
  </span>
</template>

<script>
export default {
  name: "MarkedText"
}
</script>

<style lang="scss" scoped>
.marked-text {
  color: #DD3232;
}
</style>
