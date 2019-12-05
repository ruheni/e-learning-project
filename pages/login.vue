<template>
  <div class="form">
    <b-container class="form">
      <h3>Login</h3>
      <b-form @submit.stop.prevent="login" v-if="!$store.state.authUser">
        <p v-if="formError">{{ formError }}</p>
        <!-- <p>
          <i>
            To login, use
            <b>demo</b> as username and
            <b>demo</b> as password.
          </i>
        </p>-->
        <!-- username -->
        <b-form-group id="email" label="Email address:" label-for="email">
          <b-form-input id="email" v-model="email" type="email" required placeholder="username"></b-form-input>
        </b-form-group>
        <!-- password -->
        <b-form-group id="password" label="Password:" label-for="password">
          <b-form-input
            id="password"
            v-model="password"
            type="password"
            required
            placeholder="Your password here..."
          ></b-form-input>
        </b-form-group>
        <b-button type="submit" variant="primary">Submit</b-button>
      </b-form>
    </b-container>
  </div>
</template>
<script>
const Cookie = process.client ? require('js-cookie') : undefined

export default {
  data() {
    return {
      email: '',
      password: '',
      formError: null
    }
  },
  methods: {
    async login() {
      const auth = {
        accessToken: 'authUser'
      }
      this.$store.commit('setAuth', auth)
      Cookie.set('auth', auth)
      this.$router.push('/student')
    }
  }
}
</script>
<style scoped>
.error {
  color: red;
}
.form {
  max-width: 700px;
  margin: auto;
  margin-top: 50px;
}
</style>