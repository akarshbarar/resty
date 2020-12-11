<template>
  <div class="index">
    <!-- <Navbar/> -->
    <p>hi</p>
  </div>
</template>

<script>
import Navbar from '../components/Navbar'

export default {

    head: {
    title: "Resty | Modern Rest Client",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        name: "description",
        content: "Resty is Modern day Rest Client for testing REST API's. It is also for websocket and GraphQL"
      },
      {
        name: "keyword",
        content:
          "REST Clinet, POSTMAN INSOMNIA GraphQL Websocket POST PUT GET OPTIONS HEADERS OAUTH  OAUTH2 "
      }
    ],
  },
  components:{
    Navbar,
  }


}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.index{
  flex: 1;
  background-color: black;
  width: 100vw;
  height: 100vh;
  color:aliceblue;
}

</style>
