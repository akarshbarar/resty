<template>
  
  <div class="navbar">
      <div class="index__mainNavbar">
       <h1>RESTY</h1>
       <ul>
         <li>Github</li>
         <li>Login</li>
       </ul>
     </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.navbar{
    background-color: black;
    color:white;
    padding:  10px;
}
.index__mainNavbar{
  display: flex;
  justify-content: space-between;
  font-size: large;
  font-weight: 900;
}
.index__mainNavbar>ul{
  display: flex;
  justify-content: space-evenly;
}
li{
  margin-left: 5px;
  margin-right: 20px;
}
</style>