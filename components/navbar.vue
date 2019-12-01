<template>
  <!-- <b-navbar toggleable="lg" >
    <b-nav vertical>
      <b-nav-item to="/student">Coursework</b-nav-item>
      <b-nav-item to="/student/grades">Grades</b-nav-item>
      <b-nav-item to="/student/messages">Messages</b-nav-item>
      <b-nav-item to="/student/account">My Account</b-nav-item>
    </b-nav>
  </b-navbar>-->
  <div>
    <!-- <b-navbar toggleable="lg" type="light" variant="light">
      <b-navbar-brand href="#">NavBar</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-nav-item-dropdown right>
            <template v-slot:button-content>
              <strong>User</strong>
            </template>
            <b-dropdown-item to="/student/account">Profile</b-dropdown-item>
            <b-dropdown-item href="/student/">Sign Out</b-dropdown-item>
          </b-nav-item-dropdown>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>-->
    <b-navbar type="dark" variant="dark">
      <b-navbar-brand to="/">NavBar</b-navbar-brand>
      <b-navbar-nav class="ml-auto">
        <b-nav-item v-if="username" @click="logout">
          <em>Hello {{ username }}</em>
        </b-nav-item>
        <b-nav-item v-if="$store.state.authUser" @click="logout">Logout</b-nav-item>
      </b-navbar-nav>
    </b-navbar>
  </div>
</template>
<script>
export default {
  name: 'Navbar',

  methods: {
    async logout() {
      try {
        await this.$store.dispatch('logout')
      } catch (error) {
        this.formError = error.message
      }
    }
  }
}
</script>
<style scoped>
</style>