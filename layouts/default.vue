<template>
<div>
    <Navbar/>

<div class="default">
    <Sidebar/>
    <Nuxt />
  </div>
</div>
  
</template>

<script>

import Sidebar from "../components/Sidebar"
import Navbar from "../components/Navbar"

export default {
    components:{
      Navbar,
      Sidebar
    }

}
</script>
<style>
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
    background-color: black;

}

*,
*::before,
*::after {

  box-sizing: border-box;
  margin: 0;
}
a{
  text-decoration: none;
  color: #fff;
}
li{
 list-style: none; 
}
.default{
  display: flex;
  flex-direction: row;
}
</style>
