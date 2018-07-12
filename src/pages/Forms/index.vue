<script>
import Card from 'card'
import Inputs from '@/components/Inputs'
import Buttons from '@/components/Buttons'
import Selects from '@/components/Selects'


// console.log(Card)


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
      }],
      inputData2: [{
        type: 'text',
        name: 'username',
        label: 'Name',
        style: 'half',
        vuelidate: 'alpha_spaces|min:3'
      }, {
        type: 'number',
        name: 'phone',
        label: 'Phone',
        style: 'half',
        vuelidate: 'required|decimal'
      }, {
        type: 'date',
        name: 'bithday',
        label: 'Birth Day',
        vuelidate: ''
      }],
      inputDataAdd: {
        type: 'text',
        name: 'address',
        placeholder: 'detail address',
        vuelidate: 'required'
      },
      inputData4: [{
        type: 'text',
        name: 'number',
        label: 'Card Number',
        style: 'half',
        vuelidate: 'required'
      }, {
        type: 'text',
        name: 'name',
        label: 'Cardholder Name',
        style: 'half',
        vuelidate: 'required'
      }, {
        type: 'text',
        name: 'expiry',
        label: 'Expired Day',
        style: 'half',
        vuelidate: 'required'
      }, {
        type: 'text',
        name: 'cvc',
        label: 'CVC',
        style: 'half',
        vuelidate: 'required'
      }]
    }
  },
  mounted () {
    const card = new Card({
      form: '.creditCard',
      container: '.card-wrapper',
    //   placeholders: {
    //     number: '**** **** **** ****',
    //     name: 'Arya Stark',
    //     expiry: '**/****',
    //     cvc: '***'
    // }
    })
  },
  components: {Inputs, Buttons, Selects}
}
</script>
<template src="./template.html"></template>
<style lang="scss" src="./style.scss" scoped></style>
