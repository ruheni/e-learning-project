<template>
  <div class="page">
    <div>
      <navbar />
    </div>
   <div class="wrapper">
     <!-- profile  -->
        <div class="container">
                <img id="image" src="../../assets/images/blank-profile-picture-973460_1280.png" alt="image">
                <h1 id="header"> Student Details </h1>
        </div>
       <!-- Data Section  -->
        <div class="info">
          <!-- Personal data  -->
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

            <!-- Course Data  -->
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
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-size: 1.2rem;
}
body{
    background-color: #ecf0f1;
    display: flex;
}
.wrapper{
    position: absolute;
    top: 30%;
    left: 50%;
    transform: translate(-50%, -30%); 
    width: 60%;
    box-shadow: 0 1px 20px rgba(69,90,100, 0.08);
    background-color: #ffffff;
    border-radius: 5px;
   
}
.container{
    background-color: #9eb2de;
    height: 16rem;
    padding: 2.5rem;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;
}
#image{
    position: relative;
    width: 10rem;
    height: 10rem; 
    border-radius: 50%;

}
#header{
    float:right;
    position: relative;
    top: 80%;
    font-size: 1.8rem; 
    
}
.info{
    display: flex; 
    padding: 1rem;

}
.info,h3{
    margin-bottom: 0.5rem;
    font-size: 1.3rem;

}

p{
    padding: 0.25rem;

}
.personal_info{
    flex: 1;

}
.course_info{
    flex: 1;

}
.personal_info>table{
    text-align: left;

}
td,th{
    padding: 0.25rem 0.25rem 0.25rem 0 ;
}
.units{
    margin-top: 0.5rem;
}
@media only screen and (max-width: 768px) {
    #header{
        top: 0;
        float: none;
    }
    .info{
        display: block;
    }
}
</style>