<template>
  <div>
    <b-navbar type="light" variant="light">
      <b-navbar-brand to="#">Riara E-Learning</b-navbar-brand>
      <b-navbar-nav class="ml-auto">
        <!-- dropdown -->
        <b-nav-item-dropdown text="Menu" right>
          <b-dropdown-item to="/student/">Coursework</b-dropdown-item>
          <b-dropdown-item to="/student/grades">Grades</b-dropdown-item>
          <b-dropdown-item to="/student/messages">Messages</b-dropdown-item>
          <b-dropdown-item to="/student/account">My Account</b-dropdown-item>
        </b-nav-item-dropdown>

        <!--  -->
        <b-nav-item v-if="$store.auth">
          Hello
          <em>{{ $auth.user }}</em>
        </b-nav-item>
        <b-nav-item v-if="$store.auth" @click="logout">Logout</b-nav-item>
      </b-navbar-nav>
    </b-navbar>
  </div>
</template>
<script>
const Cookie = process.client ? require('js-cookie') : undefined

export default {
  name: 'Navbar',
  data() {
    return {
    }
  },
  methods: {
    async logout() {
      Cookie.remove('auth')
      this.$store.commit('setAuth', null)
    }
  }
}
</script>
<style scoped>
</style>