<script>
import Card from 'card'
import Inputs from '@/components/Inputs'
// import Buttons from '@/components/Buttons'
import Selects from '@/components/Selects'
import axios from 'axios'

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
      }],
      city: '',
      regions: ['xx區', 'oo區'],
      nowStep: 0,
      title: ['Create Account', 'General Infomation', 'Payment Method'],
      subTitle: ['Glad to see you here!', 'Tell us who you are!', 'Add your credit card infomation!'],
    }
  },
  created () {
    axios.get('/api/data/')
      .then(res => {
        this.city = res.data
      })
      .catch(error => {
        console.log(error)
      })
  },
  mounted () {
    // new Card({
    //   form: '.creditCard',
    //   container: '.card-wrapper'
    // })
  },
  methods: {
    nextStep(){
      this.nowStep = 2;
      new Card({
        form: '.creditCard',
        container: '.card-wrapper'
      })
    }
  },
  components: {Inputs, Selects}
}
</script>
<template src="./template.html"></template>
<style lang="scss" src="./style.scss" scoped></style>
