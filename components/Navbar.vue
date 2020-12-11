<template>
  <div class="navbar">
      <header>
          <nav>
              <nuxt-link to="/"><img src="/favicon.ico"/></nuxt-link>
              <!-- <ul>
                  <li><nuxt-link to="/">About Us</nuxt-link></li>
                  <li><nuxt-link to="/">Contact us</nuxt-link></li>
              </ul> -->
          </nav>
      </header>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>

.navbar{
    top:0;
    position: sticky;
    z-index: 100; 
    background-color: #040c0e;
}
nav,ul{
    font-size: clamp(10px,2vw,25px);
    font-weight: 500;
    color: white;
    display:flex;
    flex-direction:row;
    justify-content:space-between;
    align-items: center;
    margin: 0 10px;
}
ul>li{
    margin-left: 10px;
}

</style>

