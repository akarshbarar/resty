<template>
  <div class="sidebar">
      <p>REST</p>
      <p>WebSocket</p>
      <p>GraphQL</p>
      <p>Documentation</p>
      <p>Setting</p>
      
  </div>
</template>

<script>
export default {

}
</script>

<style>
.sidebar{
    background-color: #040c0e;
    color: #fff;
    overflow-y: hidden;
    position: fixed;
    z-index: 90;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    height: 100vh;
}
</style>