<template>
  <div class="hello">
    <h1>Home</h1>
   <table>
     <thead>
       <tr>
         <th>First Name</th>
         <th>Last Name</th>
         <th>Email</th>
         <th>Address</th>
       </tr>
     </thead>
     <tbody>
       <tr v-for="(item,i) in tableData" :key="item.firstName">
         <td>{{item.firstName}}</td>
         <td>{{item.lastName}}</td>
         <td>{{item.email}}</td>
         <td>{{item.address}}</td>
       </tr>
     </tbody>
   </table>
 
  </div>
</template>

<script>
export default {
  name: 'Home',
  props:{
    goToLogin:Function
  },
  data:()=>({
   "tableData":[
   {"firstName":"Anamika","lastName":"Srivastav","email":"charu@gmail.com","address":"Niral Nagar"},
   {"firstName":"Swati","lastName":"Srivastav","email":"swati@gmail.com","address":"fghhuiii"},
   {"firstName":"Pihu","lastName":"Srivastav","email":"pihu@gmail.com","address":"Golaghat"},
   ]

  }),

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
table{
  width: 100%;
  border:1px solid black;
}
tr,th,td{
  border:1px solid black;
}
</style>
