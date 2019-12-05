<template>
  <div class="page">
    <div>
      <navbar />
    </div>
    <!-- Student Details -->
    <div class="student_data">
      <!-- <p v-for="college in colleges" :key="college.id">{{ college.college_name }}</p> -->
      <img id="image" src="../../assets/images/blank-profile-picture-973460_1280.png" alt="image" />
      <h2 id="details">{{first_name}} {{last_name}}</h2>
      <h3 id="details">{{registration_number}}</h3>
    </div>
    <div class="grade_details">
      <p>Your grades are as follows:</p>
    </div>
  </div>
</template>
<script>
import navbar from '../../components/navbar.vue'
export default {
  components: { navbar},
  middleware: 'auth',
  data() {
    return {
      first_name:'',
      last_name:'',
      registration_number:'',
      grades: [],
      colleges: []
    }
  },
  // mounted() {},
  async created() {
    const res = this.$axios
      .$get('https://damp-tundra-97364.herokuapp.com/students/1',{})
      .then(res => {
        let {
          first_name,
          last_name,
          registration_number
        }=res
        this.first_name=first_name
        this.last_name=last_name
        this.registration_number=registration_number
      })
    // console.log(first_name)
  }
}
</script>
<style scoped>
.student_data {
  background-color: #9eb2de;
  height: 16rem;
  padding: 2.5rem;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  display:flex;
  flex-flow: row wrap;
  justify-content: flex-start;
}
#details{
  padding: 10px;
}
#image {
  position: relative;
  width: 10rem;
  height: 10rem;
  border-radius: 50%;
}
</style>