<template>
  <div class="setting">
    <div class="index__mainContent">
            <h1>Settings</h1>

    </div>
  </div>
</template>

<script>
export default {

 head: {
        title: "Resty | Setting",
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
.setting{
  background-color: black;
  display: flex;
  color: aliceblue;
  width: 100vw;
  height: 100vh;
  padding: 2px;
}

.index__mainContent{
    background-color: #0A0A0A;
    margin-left: auto;
    margin-right: auto;
    margin-top: 1rem;
    width: 50vw;    
    padding: 1rem;
    border-radius: 10px;

}
</style>