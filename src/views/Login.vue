<template>
    <div>
        <form action="" v-if="!log">
          <p>用户名</p>
          <input type="text" v-model="name">
          <p>密码</p>
          <input type="password" v-model="psw">
          <div>
              <button type="button" @click="login()">登陆</button>
              <button type="button" @click="reg()">注册</button>
          </div>
        </form>
         <form action="" v-else>
          <p>用户名</p>
          <input type="text" v-model="name">
          <p>密码</p>
          <input type="password" v-model="psw">
          <p>再次输入密码</p>
          <input type="password" v-model="psw2">
          <div>
              <button type="button" @click="adduser()">确定</button>
              <button type="button" @click="cancel()">取消</button>
          </div>
        </form>
    </div>
</template>
<script>
export default {
  name: 'Login',
  data () {
    return {
      log: false,
      name: '',
      psw: '',
      psw2: '',
      repeat: ''
    }
  },
  methods: {
    login () {
      if (localStorage.getItem('name') === this.name && localStorage.getItem('psw') === this.psw) {
        this.name = ''
        this.psw = ''
        this.$router.push('/home/list')
      }
    },
    reg () {
      this.log = true
    },
    adduser () {
      if (this.psw === '') {
        alert('请输入密码')
        return
      }
      if (this.psw2 === '') {
        alert('请确认密码')
        return
      }
      if (this.psw2 !== this.psw) {
        alert('两次密码不一致')
        return
      }
      localStorage.setItem('name', this.name)
      localStorage.setItem('psw', this.psw)
      this.name = ''
      this.psw = ''
      this.log = false
    },
    cancel () {
      this.log = false
    }
  }
}
</script>
<style scoped>

</style>
