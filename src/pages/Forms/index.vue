<script>
import Inputs from '@/components/Inputs'
import Buttons from '@/components/Buttons'
export default {
  name: 'forms',
  data() {
    return {
      inputData1: [{
        type: 'text',
        name: 'account',
        label: 'Account',
        vuelidate: 'required|email'
      }, {
        type: 'password',
        name: 'pw',
        label: 'Password',
        vuelidate: 'required|min:8'
      }, {
        type: 'password',
        name: 'confirmpPw',
        label: 'Confirm Password',
        vuelidate: 'required|confirmed:pw'
      }]
    }
  },
  components: {Inputs, Buttons}
}
</script>
<template src="./template.html"></template>
<style lang="scss" src="./style.scss" scoped></style>
