<template lang="">
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="username">id:</label>
      <input id="username" type="text" v-model="username">
    </div>
    <div>
      <label for="password">pw:</label>
      <input id="password" type="text" v-model="password">
    </div>
    <button type="submit">login</button>
  </form>
</template>
<script>
import axios from 'axios'; //임포트 사용할 변수명 from 엑시오스
export default {
  data: function(){
    return {
      username:'',
      password:'',
    }
  },
  methods : {
    submitForm : function(){
      // event.preventDefault(); //바닐라js 혹은 제이쿼리에서 새로고침을 막는 코드
      // vue에서는 html에 코드에  .prevent 를 붙인다.
      console.log(this.username, this.password);
      var url = 'https://jsonplaceholder.typicode.com/users';
      var data = {
        username: this.username,
        password: this.password
      }
      //포스트의 규칙은 첫번쨰인자 url, 두번째 인자 data
      axios.post(url, data)
        .then(function(response) {
          console.log(response);
        })
        .catch(function(error) {
          console.log(error);
        })
    }
  }
}
</script>
<style lang="">
  
</style>