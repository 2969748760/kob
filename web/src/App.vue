<template>
  <NavBar/>
  <router-view></router-view>
</template>

<script>
import NavBar from './components/NavBar.vue'
import "bootstrap/dist/css/bootstrap.min.css"
import "bootstrap/dist/js/bootstrap"
import $ from 'jquery'

export default {
  components: {
    NavBar
  },
  setup() {
    $.ajax({
      url: "http://localhost:3000/user/account/token/",
      type: "post",
      data: {
        username: 'zzx',
        password: '123456',
      },
      success(resp) {
        console.log(resp);
      },
      error(resp) {
        console.log(resp);
      }
    })

    $.ajax({
      url: "http://localhost:3000/user/account/info/",
      type: "get",
      headers: {
        Authorization: "Bearer " + "eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJlNjczNDEwOTBhNDk0ZGQwOGQ3ZjlhM2EzYTIyY2VkMSIsInN1YiI6IjgiLCJpc3MiOiJzZyIsImlhdCI6MTcyMTc0MTIzMCwiZXhwIjoxNzIyOTUwODMwfQ.uWQHfaJTMW3VTHgiDwDqFaDK_33quXq1UK5DuNUJJ4k"
      },
      success(resp) {
        console.log(resp);
      },
      error(resp) {
        console.log(resp);
      }
    })

    // $.ajax({
    //   url: "http://localhost:3000/user/account/register/",
    //   type: "post",
    //   data: {
    //     username: "zzx2",
    //     password: "zzx220011214",
    //     confirmedPassword: "zzx220011214",--;.dfgtrged`  5`    
    //   },
    //   success(resp) {
    //     console.log(resp);
    //   },
    //   error(resp) {
    //     console.log(resp);
    //   }
    // })
  }
}
</script>

<style>
body {
  background-image: url("@/assets/images/background.png");
  background-size: cover;
}
</style>

