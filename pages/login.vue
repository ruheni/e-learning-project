<template>
  <div class="form">
    <b-container>
      <b-form @submit.stop.prevent="login" v-if="!$store.state.authUser">
        <p v-if="formError">{{ formError }}</p>
        <p>
          <i>
            To login, use
            <b>demo</b> as username and
            <b>demo</b> as password.
          </i>
        </p>
        <!-- username -->
        <b-form-group id="email" label="Email address:" label-for="email">
          <b-form-input id="email" v-model="username" type="text" required placeholder="username"></b-form-input>
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
export default {
  data() {
    return {
      username: '',
      password: '',
      formError: null
    }
  },
  methods: {
    async login() {
      try {
        await this.$store.dispatch('login', {
          username: this.username,
          password: this.password
        })
        this.username = ''
        this.password = ''
      } catch (error) {
        this.formError = error.message
      }
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
  margin: 20px auto;
}
</style>