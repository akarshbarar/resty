<template>
  <div class="index">
   <div class="index__main">
     <div class="index__mainContent p-1">
            <div class="requestname">Request Name</div>
            <input type="text" placeholder="Enter Request Name"/>
            <div class="mt-8 table w-full ...">
                  <div class="table-row-group">
                    <div class="table-row">
                      <div class="table-cell ...">METHOD</div>
                      <div class="table-cell ...">URL</div>
                    </div>
                    <div class="table-row">
                      <div class="table-cell ...">Cell 4</div>
                      <div class="table-cell ..."><input type="url" placeholder="Enter URL"/></div>
                    </div>
                  </div>
                </div>
            
     </div>
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
  margin-top: 5px;
}
.index__mainContent{
    background-color: #0A0A0A;
    margin-left: 50px;
    width: 50vw;    
    padding: 5px;
    border-radius: 10px;

}

</style>
