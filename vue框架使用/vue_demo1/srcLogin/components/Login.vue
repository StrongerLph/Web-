<template>
  <div>
    <div id="show-login" @click="show = !show" v-if="!show">Show Login Form</div>

    <transition name="loginbox">
      <div id="login-box" v-if="show">
        <div id="hide-login" @click="show = !show">X</div>
        <form action=javascript:; id="login-form">
          <h1>Welcome</h1>
          <input type="text" placeholder="Username" class="inp">
          <input type="password" placeholder="Password" class="inp">
          <input type="submit" value="Login" class="login-sub">
        </form>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      show: false
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

body {
  background-color: black;
}

#login-box {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100vh;
  background-color: rgb(61, 60, 60);
  z-index: 9999;
}

#login-form {
  position: absolute;
  left: 45%;
  top: 40%;
  color: #fff;
  text-align: center;
}

.inp {
  display: block;
  box-sizing: border-box;
  width: 240px;
  padding: 10px 20px;
  background-color: rgb(160, 159, 159);
  color: #fff;
  border: 1px solid #fff;
  border-radius: 5px;
  text-align: center;
  outline: none;
  margin: 10px 0;
}

.login-sub {
  width: 240px;
  padding: 10px;
  background-color: rgb(5, 32, 66);
  border: 1px solid rgb(179, 177, 177);
  border-radius: 5px;
  text-align: center;
  color: #fff;
  cursor: pointer;
}

.login-sub:hover {
  background-color: rgb(5, 89, 192);
}

#hide-login {
  width: 30px;
  height: 30px;
  line-height: 30px;
  border-radius: 50%;
  text-align: center;
  background-color: rgba(170, 167, 167, 0.7);
  color: #000;
  position: absolute;
  top: 40px;
  right: 40px;
  cursor: pointer;
}

#hide-login:hover {
  color: #fff;
  background-color: rgb(247, 57, 57);
  border: 1px solid #fff;
}

#show-login {
  position: absolute;
  top: 45%;
  left: 45%;
  padding: 10px 20px;
  border: 1px solid rgb(255, 255, 255);
  border-radius: 5px;
  text-align: center;
  font-size: 26px;
  color: #fff;
  user-select: none;
  cursor: pointer;
}

#show-login:hover {
  background-color: rgb(46, 235, 39);
}

.loginbox-enter,
.loginbox-leave-to {
  transform: translateX(-100%);
}

.loginbox-enter-active,
.loginbox-leave-active {
  transition: all 2s ease;
}
</style>
