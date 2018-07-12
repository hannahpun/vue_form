<script>
export default {
  name: 'selects',
  props: {
    options: {
      type: [Array, String],
      default: null
    }
  }
}
</script>

<template src="./template.html"></template>
<style lang="scss" src="./style.scss" scoped></style>
