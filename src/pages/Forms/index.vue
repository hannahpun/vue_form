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
      imagesList: [],
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
        vuelidate: 'required'
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
      title: ['Create Account', 'General Infomation', 'Update Profile Picture',  'Payment Method'],
      subTitle: ['Glad to see you here!', 'Tell us who you are!','We wanna know you more!',  'Add your credit card infomation!']
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
    readmultifiles (e) {
      var files = e.target.files //fileList Obj
      // console.log(e.target.files)
      var vm = this;
      var reader = new FileReader();  
      function readFile(index) {
        if( index >= files.length || index > 2) return;
        var file = files[index];
        reader.onload = function(e) {  
          // get file content  
          // var bin = e.target.result;
          
          vm.imagesList.push(e.target.result)
          // debugger;
          // do sth with bin
          readFile(index+1)
        }
        reader.readAsDataURL(file);
      }
      readFile(0);

      // console.log('dddd', vm.imagesList)
      //FileReader
      // var vm = this;
      // var reader = new FileReader();
      // //當讀取完時
      // reader.onload = () => {
      //     vm.imagesList.push(reader.result)
      //     console.log(reader.result)
      // }
      // //讀取檔案並以 URL 格式存放
      // reader.readAsDataURL(e.target.files[0])
    },
    nextStep() {
      this.nowStep = 2
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
