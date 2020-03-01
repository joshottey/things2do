<template>
  <div>
    <h1>Register</h1>
    <input type="email" name="email" v-model="email">
    <input type="password" name="password" v-model="password">
    <button @click="register" type="button">Register</button>
    <p v-if="response">{{ response.data.message }}</p>
  </div>
</template>

<script>
import AuthService from '@/services/AuthService'
export default {
  name: 'Register',
  data () {
    return {
      email: '',
      password: '',
      response: null,
    }
  },
  methods: {
    async register () {
      this.response = await AuthService.register({
        email: this.email,
        password: this.password,
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
