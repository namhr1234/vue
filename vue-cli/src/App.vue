<template>
  <div>
  <!--  <app-header v-bind:props속성이름="상위컴포넌트의 데이터 이름"></app-header> -->
  <app-header v-bind:propsdata="str" v-on:renew="renewStr"></app-header>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
//import 하는 경로를 받아와서 AppHeader라는 변수로 받아온다 .아래와 같다.
// var AppHeader = {
  // template : {
    // '<header><h1>Header</h1></header>'
 // }
//}

// new Vue ({
//   date : {
//     str : 'hi'
//   }
// })

export default {
  data : function() {
    return {
      str : 'Header1'
    }
  },
  components: {
    'app-header' : AppHeader
  },
  methods : {
    renewStr : function(){
      this.str = 'hiiii'
    }
  }
}
</script>

<style>

</style>