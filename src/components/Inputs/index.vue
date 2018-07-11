<script>
export default {
  name: 'inputs',
  props: {
    type: {
      type: String,
      default: 'text'
    },
    name: {
      type: String,
      default: null
    },
    label: {
      type: String,
      default: null
    },
    item: {
      type: Object,
      default: null
    }
  }
}
</script>

<template src="./template.html"></template>
<style lang="scss" src="./style.scss" scoped></style>
