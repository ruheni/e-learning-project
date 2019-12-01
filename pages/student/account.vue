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
            <td>Jane{{name}}</td>
          </tr>

          <tr>
            <th>Registration No:</th>
            <td>Hdb212-0040/1027 {{regNo}}</td>
          </tr>

          <tr>
            <th>Email:</th>
            <td>emailaddress@gmail.com {{email}}</td>
          </tr>

          <tr>
            <th>Year of Study:</th>
            <td>2 {{year}}</td>
          </tr>

          <tr>
            <th>Semester:</th>
            <td>2{{semester}}</td>
          </tr>
        </table>
        <table class="personal_info">
          <tr>
            <th>Gender:</th>
            <td>Gender {{Gender}}</td>
          </tr>

          <tr>
            <th>Telephone no:</th>
            <td>Telephone no {{telNo}}</td>
          </tr>

          <tr>
            <th>Nationality:</th>
            <td>Nationality {{nationality}}</td>
          </tr>

          <tr>
            <th>ID No</th>
            <td>id {{ID}}</td>
          </tr>

          <tr>
            <th>Sponsor</th>
            <td>sponsor {{sponsor}}</td>
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
    return {}
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
  margin-top: 20px;
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