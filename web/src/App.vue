<template>
  <NavBar />
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
        password: 'zzx20011214',
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
        Authorization: "Bearer "+"eyJhbGciOiJIUzI1NiJ9.eyJqdGkiOiJhMDY3NzQwMjgxMzY0OTc5YTljNjAzMmI5ZWRhMjZkMSIsInN1YiI6IjEiLCJpc3MiOiJzZyIsImlhdCI6MTY2NzY1OTY2NiwiZXhwIjoxNjY4ODY5MjY2fQ.9bl2titCMuFR5c5UvLmagFpFTRjxwHsD6QmhF3AJPsg"
      },
      success(resp) {
        console.log(resp);
      },
      error(resp) {
        console.log(resp);
      }
    })

    $.ajax({
      url: "http://localhost:3000/user/account/register/",
      type: "post",
      data: {
        username: "zzx2",
        password: "zzx220011214",
        confirmedPassword: "zzx220011214",
      },
      success(resp) {
        console.log(resp);
      },
      error(resp) {
        console.log(resp);
      }
    })
  }
}
</script>

<style>
body {
  background-image: url("@/assets/images/background.png");
  background-size: cover;
}
</style>

