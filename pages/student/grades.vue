<template>
  <div class="page">
    <div>
      <!-- <navbar /> -->
    </div>
    <div>
      <h1>Grades page here</h1>
      <p v-for="college in colleges" :key="college.id">{{ college.college_name }}</p>
    </div>
  </div>
</template>
<script>
// import navbar from '../../components/navbar.vue'
export default {
  components: {},
  middleware: 'auth',
  data() {
    return {
      grades: [],
      colleges: []
    }
  },
  mounted() {},
  async created() {
    const res = this.$axios
      .$get('http://localhost:1337/colleges',{})
      .then(res => (this.colleges = res))
    // console.log
  }
}
</script>
<style scoped>
</style>