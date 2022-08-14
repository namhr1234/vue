<template>
  <form v-on:submit.prevent="submitForm"> <!-- 새로고침 방지해주는 prevent -->
    <div>
      <label for="username">id</label>
      <input id="username" type="text" v-model="username">
    </div>
    <div>
      <label for="password">password</label>
      <input id="password" type="password">

    </div>
    <button type="submit">login</button>
  </form>
</template>



<script>

import axios from 'axios'

export default {
  data: function(){
    return {
      username : '',
      password : ''
    }
  },
  methods: {
    submitForm : function(){
    ///  event.preventDefault();
      console.log(this.username, this.password);
     
      var url = "https://jsonplaceholder.typicode.com/users"
      var data = {
        username: this.username,
        password:  this.password
      }
       axios.post(url, data)
       .then(function(response){
        console.log(response)
       }
       ).catch(function(error){
        console.log(error)
       }); // axios : http 통신 프로토콜 해주는 라이브러리 //post: 데이터를 생성할때 씀
    }
  }
}
</script>

<style>

</style>