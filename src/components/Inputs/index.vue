<script>
export default {
  name: 'inputs',
  props: {
    type: {
      type: String,
      default: 'text'
    },
    label: {
      type: String,
      default: null
    }
  }
}
</script>

<template src="./template.html"></template>
<style lang="scss" src="./style.scss" scoped></style>
