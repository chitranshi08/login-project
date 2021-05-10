<template>
  <div class="hello">
    <h1>Login</h1>
   <label>Email</label>
   <input v-model="email" type="text" placeholder="Email"><br>
   <label>Password</label>
   <input v-model="password" type="password" placeholder="Password"><br>

   <button @click="submit">Login</button>
 
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props:{
    goToHome:Function
  },
  data:()=>({
    "password":"",
    "email":""
  }),
  methods:{
    submit(){
      if(!this.password || !this.email){
        return;
      }
      if(this.password && this.password.length < 8){
        alert("Password should have atleast 8 character")
        return;
      }
      if(this.password && !this.password.match(/^[A-Za-z0-9!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~]{8,}$/)){
        alert("Password should have atleast one special character, one capital letter and one number")
        return;
      }
      
      if(this.email && !this.email.match(/(.+)@(.+){2,}\.(.+){2,}/)){
        alert("Please enter valid email")
        return;
      }
      this.goToHome()
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
