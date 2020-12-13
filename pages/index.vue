<template>
  <div class="index">
   <div class="index__main">
     <div class="index__mainContent p-1">
            <div class="requestname">Request Name</div>
            <input type="text" placeholder="Enter Request Name"/>
            <div class="mt-8 table w-full ...">
                  <div class="table-row-group">
                    <div class="table-row">
                      <div class="table-cell text-xl ...">METHOD</div>
                      <div class="table-cell text-xl...">URL</div>
                    </div>
                    <div class="table-row">
                      <div class="table-cell ...">

                        <div class="dropdown">
                          <button class="dropbtn">Dropdown</button>
                          <div class="dropdown-content">
                          <a href="#">Link 1</a>
                          <a href="#">Link 2</a>
                          <a href="#">Link 3</a>
                          </div>
                        </div>
                      </div>
                      <div class="table-cell ..."><input type="url" placeholder="Enter URL"/></div>
                      <div class="table-cell ..."><button class="">Message</button></div>

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
.dropbtn {
  padding: 16px;
  font-size: 16px;
  border: none;
  cursor: pointer;
}

.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {background-color: #f1f1f1}

.dropdown:hover .dropdown-content {
  display: block;
}

.dropdown:hover .dropbtn {
  background-color: #3e8e41;
}

</style>
