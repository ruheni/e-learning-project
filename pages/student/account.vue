<template>
  <div class="page">
    <div>
      <navbar />
    </div>
   <div class="wrapper">
        <div class="container">
                <img id="image" src="blank-profile-picture-973460_1280.png" alt="image">
                <h1 id="header"> Student Details </h1>
        </div>
       
        <div class="info">
            <div class="personal_info">
                <h3>Personal Details</h3>
                <table>
                    <tr>
                      <th>Name:</th>
                      <td id="name">Jane</td>
                    </tr>
        
                    <tr>    
                      <th>Registration No:</th>
                      <td id= "regNo">Hdb212-0040/1027</td>
                    </tr>
        
                    <tr>    
                        <th>Email:</th>
                        <td id= "email">emailaddress@gmail.com</td>
                      </tr>
        
                      <tr>    
                        <th>Year of Study:</th>
                        <td id= "year">2</td>
                      </tr>
        
                      <tr>    
                        <th>Semester:</th>
                        <td id= "semester">2</td>
                      </tr>
                    
                  </table>
                
            </div>

            <div class="course_info">
                <h3>Course Details</h3>
                <h4>Course</h4>
                <p id="course_code">course Name</p>
                <h4 class="units">Units</h4>
                <p id="unit1">Unit Name</p>
                <p id="unit2">Unit Name</p>
                <p id="unit3">Unit Name</p>
                <p id="unit4">Unit Name</p>
                <p id="unit5">Unit Name</p>
                <p id="unit6">Unit Name</p>
            </div>
        </div>
    </div>
  </div>
</template>
<script>
import navbar from '../../components/navbar.vue'
export default {
  components: { navbar },
  data() {
    return {}
  }
}
</script>
<style scoped>

</style>