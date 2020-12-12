<template>
  <div class="index">
   <div class="index__main">
     <h1>hi</h1>
   </div>
  </div>
</template>

<script>
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


}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.index{
  background-color: black;
  display: flex;
  color: aliceblue;
  width: 100vw;
  height: 100vh;
  padding: 2px;
}

.index__main{
  flex: 5;
  padding: 5px;
}

</style>
