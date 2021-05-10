<template>
  <div class="hello">
    <h1>Sign Up</h1>
  <img  class="user-profile" src="./../assets/user-profile.png" alt=""><br>   
   <label>First Name:</label>
   <input v-model="firstName" type="text" placeholder="first name"><br>
   <label>Last Name:</label>
   <input  v-model="lastName" type="text" placeholder="last name"><br>
   <label>Email</label>
   <input v-model="email" type="text" placeholder="email"><br>
   <label>About me</label>
   <textarea></textarea><br>
   <button @click="submit">submit</button>
 
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data:()=>({
    "firstName":"",
    "lastName":"",
    "email":""
  }),
  methods:{
    submit(){
      if(this.firstName && !this.firstName.match(/^[A-Za-z0-9]+$/)){
        alert("No special character allowed in first name")
        return;
      }
      if(this.lastName && !this.lastName.match(/^[A-Za-z0-9]+$/)){
        alert("No special character allowed last name")
        return;
      }
      if(this.email && !this.email.match(/(.+)@(.+){2,}\.(.+){2,}/)){
        alert("Please enter valid email")
      }

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .user-profile{
    width:100px;
  }
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
