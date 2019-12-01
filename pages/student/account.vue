<template>
  <div class="page">
    <navbar />
    <div class="wrapper">
      <!-- profile  -->
      <div class="container">
        <img id="image" src="../../assets/images/blank-profile-picture-973460_1280.png" alt="image" />
        <h1 id="header">Student Details</h1>
      </div>
      <!-- Data Section  -->
      <h3>Personal Details</h3>
      <div class="info">
        <table class="personal_info">
          <tr>
            <th>Name:</th>
            <td>{{ first_name}} {{ last_name }}</td>
          </tr>

          <tr>
            <th>Registration No:</th>
            <td>{{ registration_number }}</td>
          </tr>

          <tr>
            <th>Email:</th>
            <td>{{ school_email }}</td>
          </tr>
          <tr>
            <th>Course</th>
            <td>{{ course }}</td>
          </tr>

          <tr>
            <th>Year of Study:</th>
            <td>2 </td>
          </tr>

          <tr>
            <th>Semester:</th>
            <td>2</td>
          </tr>
        </table>
        <table class="personal_info">
          <tr>
            <th>Gender:</th>
            <td>Male</td>
          </tr>

          <tr>
            <th>Telephone no:</th>
            <td>0{{phone_number}}</td>
          </tr>

          <tr>
            <th>Nationality:</th>
            <td>Kenyan</td>
          </tr>

          <tr>
            <th>ID No</th>
            <td>{{ national_IDno}}</td>
          </tr>

          <tr>
            <th>Sponsor</th>
            <td>Parent</td>
          </tr>
        </table>
      </div>
    </div>
  </div>
</template>
<script>
import navbar from '../../components/navbar.vue'
export default {
  components: { navbar },
  middleware: 'auth',
  data() {
    return {
      first_name: '',
      last_name: '',
      registration_number: '',
      school_email: '',
      course: '',
      phone_number: '',
      national_IDno: ''
    }
  },
  async created() {
    const res = this.$axios
      .$get('https://damp-tundra-97364.herokuapp.com/students/1')
      .then(res => {
        let {
          first_name,
          last_name,
          registration_number,
          school_email,
          course,
          phone_number,
          national_IDno
        } = res
        this.first_name = first_name
        this.last_name = last_name
        this.registration_number = registration_number
        this.school_email = school_email
        this.course = course.course_name
        this.phone_number = phone_number
        this.national_IDno = national_IDno
        console.log(first_name)
      })
  }
}
</script>
<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-size: 1.2rem;
}
body {
  background-color: #ecf0f1;
  display: flex;
}
.wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-items: center;
  position: relative;
  box-shadow: 0 1px 20px rgba(69, 90, 100, 0.08);
  background-color: #ffffff;
  border-radius: 5px;
  margin: 20px auto;
  max-width: 800px;
}
@media screen and (max-width: 600px) {
  .wrapper {
    margin: 30px;
  }
}
.container {
  background-color: #9eb2de;
  height: 16rem;
  padding: 2.5rem;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
}
#image {
  position: relative;
  width: 10rem;
  height: 10rem;
  border-radius: 50%;
}
#header {
  float: right;
  position: relative;
  top: 80%;
  font-size: 1.8rem;
}
.info {
  display: flex;
  padding: 1rem;
}
.info,
h3 {
  margin-bottom: 0.5rem;
  font-size: 1.3rem;
}

p {
  padding: 0.25rem;
}
.personal_info {
  flex: 1;
}
.course_info {
  flex: 1;
}

.personal_info > table {
  text-align: left;
}
td,
th {
  padding: 0.25rem 0.25rem 1.5rem 0;
}
.units {
  margin-top: 0.5rem;
}
@media only screen and (max-width: 768px) {
  #header {
    top: 0;
    float: none;
  }
  .info {
    display: block;
  }
}
</style>