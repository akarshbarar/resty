<template>
  <div class="index">
   <div class="index__main">
     <div class="index__mainContent">
            <div class="requestname">Request Name</div>
            <input type="text" placeholder="Enter Request Name"/>
            <table>
              <thead>
                <td><h3>METHODS</h3></td>
                <td><h3>URL</h3></td>
              </thead>
              <tbody>
                <td>
                      <div class="dropdown">
                        <select class="dropbtn" v-model="method">
                            <option value="get">GET</option>
                            <option value="post">POST</option>
                            <option value="put">PUT</option>
                            <option value="delete">DELETE</option>
                            <option value="patch">PATCH</option>
                            
                          </select>
                        </div>
                </td>
                <td>
                 <div class="container">
                    <div class="container__item">
                      <form class="form">
                        <input type="url" class="form__field" v-model="url" placeholder="Enter REST API URL" />
                        <button @click.prevent="send" class="btn btn--primary btn--inside uppercase">Send</button>
                      </form>
                    </div>
                  </div>
                </td>
              </tbody>
            </table>
      
            
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
    data:{
          url:'',
          method:'GET',
          result:'',
          resultCode:''
      
    },
    methods:{
        async send(){
          console.log(this.url);
          console.log(this.method);
          this.result = await this.$http.$get('https://api.nuxtjs.dev/posts')
          console.log(this.result);
        }
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
    margin-left: auto;
    margin-right: auto;
    width: fit-content;    
    padding: 1rem;
    border-radius: 10px;

}
table,td{
  margin-top: 1rem;
     /* border: 1px solid red; */
}
select::-ms-expand {
    display: none;
}         
select{
-moz-appearance: none; 
                    -webkit-appearance: none; 

}
.dropbtn {
  padding: 12px;
  font-size: 16px;
  border: none;
  cursor: pointer;
  background-color: #6c7ff2;

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
  background-color: #6c7ff2;
}


.container {
  display: -webkit-box;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
          flex-direction: column;
  -webkit-box-align: center;
          align-items: center;
  -webkit-box-pack: center;
          justify-content: center;
}

.uppercase {
  text-transform: uppercase;
}

.btn {
  display: inline-block;
  background: transparent;
  color: inherit;
  font: inherit;
  border: 0;
  outline: 0;
  padding: 0;
  -webkit-transition: all 200ms ease-in;
  transition: all 200ms ease-in;
  cursor: pointer;
}
.btn--primary {
  background: #7f8ff4;
  color: #fff;
  box-shadow: 0 0 10px 2px rgba(0, 0, 0, 0.1);
  border-radius: 2px;
  padding: 12px 36px;
}
.btn--primary:hover {
  background: #6c7ff2;
}
.btn--primary:active {
  background: #7f8ff4;
  box-shadow: inset 0 0 10px 2px rgba(0, 0, 0, 0.2);
}
.btn--inside {
  /* margin-left: -96px; */
}

.form{
  display: flex;
}
.form__field {
  width: 360px;
  background: #fff;
  color: #a3a3a3;
  font: inherit;
  box-shadow: 0 6px 10px 0 rgba(0, 0, 0, 0.1);
  border: 0;
  outline: 0;
  padding: 12px 18px;
}

@media 
only screen and (max-width: 1052px)
{

.form{
  display: flex;
  flex-direction: column;
}

}
</style>
