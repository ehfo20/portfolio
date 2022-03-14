<template>
  <div class="main">
    <h1 class="title">로그인</h1>
    
    <div class="flex space">
      <div class="flex login-box">
        <span class="guide">아이디</span>
        <input class="margin input" type="text" v-model="username">
      </div>
      <div class="flex login-box">
        <span class="guide">비밀번호</span>
        <input class="margin input" type="text" v-model="password">
      </div>
    </div>

    <div class="flex">
      <input class="margin button" type="button" value="로그인" @click="login">
      <input class="margin button" type="button" value="회원가입" @click="gotoRegister">
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
    }
  },
  methods: {
    gotoRegister() {
      this.$router.push('/register')
    },
    login() {
      if (this.username !== localStorage.getItem('id')) {
        window.alert('아이디를 확인해주세요')
        return
      }
      else if (this.password !== localStorage.getItem('pwd')) {
        window.alert('비밀번호를 확인해주세요')
        return
      }

      window.alert('로그인 되었습니다')
    }
  },
  mounted() {
    console.log(localStorage)
  }
}
</script>

<style scoped>
.main {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.flex {
  display: flex;
  flex-direction: column;
}

.margin {
  margin-bottom: 20px;
}

.space {
  margin-bottom: 30px;
}

.display-flex {
  display: flex;
}

.login-box {
  min-width: 250px;
  justify-content: space-between;
}

.input {
  box-sizing: border-box;
  border-color: aquamarine;
  border-radius: 10px;
  outline: none;

  padding-left: 10px;
}

.button {
  width: 250px;
  height: 25px;
  color: gray;
  background-color: #ccff00;
  border-width: 0px;
}

.button:hover {
  background-color: #f8ffdb;
}

.title {
  color: royalblue;
}

.guide {
  color: lightcoral;
  font-weight: bold;
}
</style>