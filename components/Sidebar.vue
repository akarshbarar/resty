<template>
  <div class="sidebar">
      <p><nuxt-link to="/">REST</nuxt-link></p>
      <p><nuxt-link to="/websocket">Websocket</nuxt-link></p>
      <p><nuxt-link to="/graphql">GraphQL</nuxt-link></p>
      <p><nuxt-link to="/documentation">Documentation</nuxt-link></p>
      <p><nuxt-link to="/setting">Setting</nuxt-link></p>
      
  </div>
</template>

<script>
export default {

}
</script>

<style>
.sidebar{
  background-color: #0A0A0A;
color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
}
</style>