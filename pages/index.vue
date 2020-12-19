<template>
  <div class="index">
   <div class="index__main">
     <div class="withHistory">
       <div class="index__mainContent">
            <div class="requestname">Request Name</div>
            <input type="text" class="form__field" v-model="requestName" placeholder="Enter Request Name"/>
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
       
       <div class="index__mainContent history">
         <h2>History <button @click.prevent="deleteAll()" class="btn btn--primary btn--inside uppercase">Clear History</button></h2>
          <ul v-for="item in historyDb" :key="item">
          <li class="historyCode">
          
            <p><h4> {{ item["METHOD"] }}</h4> </p>
            <p>&#9728;</p>
            <p><h4>  {{ item["STATUS CODE"] }}</h4></p>
            <p>&#9728;</p>
            <p><h4> {{ item["REQUEST NAME"] }}</h4></p>
            <button @click.prevent="deleteURL(item)" class="btn btn--primary btn--inside uppercase">Delete</button>
          </li>
          
          <li>
           <p> {{ item["URL"] }} </p>
          </li>
         
        </ul>
       </div>
     </div>
     <div class="index__mainContent" v-if="method=='post' || method=='put' || method=='delete' || method=='patch'">

<div style="display:flex; flex-direction:row;">
     <h2>Content Type:</h2>
     <select class="dropbtn" >
        <option >application/json</option>
        <option >application/vnd.api+json</option>
        <option >application/hal+json</option>
        <option >application/xml</option>
        <option >application/x-www-form-urlencoded</option>
        <option>text/html</option>
        
      </select>
    
</div>
<div class="worko-tabs">
  
    <input class="state" type="radio" title="tab-one" name="tabs-state" id="tab-one" checked />
    <input class="state" type="radio" title="tab-two" name="tabs-state" id="tab-two" />
    <input class="state" type="radio" title="tab-three" name="tabs-state" id="tab-three" />
    <input class="state" type="radio" title="tab-four" name="tabs-state" id="tab-four" />

    <div class="tabs flex-tabs">
        <label for="tab-one" id="tab-one-label" class="tab">Parameters</label>
        <label for="tab-two" id="tab-two-label" class="tab">Headers</label>
        <label for="tab-three" id="tab-three-label" class="tab">Authentication</label>
        <label for="tab-four" id="tab-four-label" class="tab">Body</label>


        <div id="tab-one-panel" class="panel active">
        <h1>Parameters</h1>          
        </div>
        <div id="tab-two-panel" class="panel">
            <h1>Headers</h1>
        </div>
        <div id="tab-three-panel" class="panel">
            <h1>Authentication</h1>
        </div>
       <div id="tab-four-panel" class="panel">
            <textarea cols="50" rows="20"/>
        </div>

    </div>

</div>


       </div>

     <div class="index__mainContent result">
       <div>Status Code: {{resultCode}}</div>
       <h1>Result</h1>
      <pre>{{ result  }}</pre>
     </div>
   </div>
  </div>
</template>

<script>
// https://stackoverflow.com/questions/33545779/xmlhttprequest-setrequestheader-for-each-request
import db from '../content/db'
export default {

  mounted(){


  },
  
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
    data(){
      return{
          url:'',
          method:'get',
          result:'',
          resultCode:'',
          requestName:null,
          historyDb:[]
      }
     
    },
  
    methods:{
      deleteURL:function(item){
          console.log(item);
          const index = db.indexOf(item);
            if (index > -1) {
              db.splice(index, 1);
            }
            this.historyDb=db

      },
      deleteAll:function(){
          db.splice(0,db.length)
          this.historyDb=[]

      },
        async send(){
                var getJSON = function(method,url, callback) {
                  var xhr = new XMLHttpRequest();
                  xhr.open(method, url, true);
                  xhr.responseType = 'json';
                  xhr.onload = function() {
                    var status = xhr.status;
                    if (status === 200) {
                      callback('200', xhr.response);
                    } else {
                      callback(status, xhr.response);
                    }
                  };
                  xhr.send();
              };
              getJSON(this.method,this.url,(status,data)=>{
                this.resultCode=status
                if(status=='404'){
                  this.result=`{'message':'Not Found'}`
                }
                else{
                this.result=data;
                  db.push({
                    "REQUEST NAME":this.requestName==null?"Untitiled Request":this.requestName,
                    "URL":this.url,
                    "METHOD":this.method,                                                                                                 
                    "STATUS CODE":this.resultCode
                  });
                  this.historyDb=db;
                  console.log(db);
                }
              });
         
       
        }
    },                                                                                                        
    


}
</script>

<style lang="scss" scoped>

/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/

/* Hide scrollbar for Chrome, Safari and Opera */
*::-webkit-scrollbar {
  display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
* {
  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;  /* Firefox */
}
.index{
  background-color: black;
  display: flex;
  color: aliceblue;
  width: 100vw;
  height: 100vh;
  padding: 2px;
}

.result{
  height: 300px;
  overflow-y:scroll ;
  width: 300px;


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
    margin-top: 1rem;
    width: 50vw;    
    padding: 1rem;
    border-radius: 10px;

}
.history{
  width:20vw ;
  height: 300px;
    overflow-y:scroll ;

}
.withHistory{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
table,td{
  padding: 1rem;
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

.historyCode{
  color: #6c7ff2;
  text-transform: uppercase;
  display: flex;
  flex-direction: row;
  margin-top: 10px;
  padding: 5px;

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
  width: clamp(20px,20vw,360px);
  background: #fff;
  color: #a3a3a3;
  font: inherit;
  box-shadow: 0 6px 10px 0 rgba(0, 0, 0, 0.1);
  border: 0;
  outline: 0;
  padding: 12px 18px;
}

@media 
only screen and (max-width: 1352px)
{

.form{
  display: flex;
  flex-direction: column;
}
.history{
  display: none;
}

}
/* PRETIFY JSON */


pre {
  padding: 5px;
  margin: 5px;
        word-break: break-all;

}


/* tabs */




/* Android 2.3 :checked fix */
@keyframes fake {
    from {
        opacity: 1;
    }
    to {
        opacity: 1;
    }
}
body {        
    animation: fake 1s infinite;
}

.worko-tabs {
    margin: 20px;
  	width: 80%;
  
    .state{
      position: absolute;
      left: -10000px;
    }
  
    .flex-tabs{
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
        
        .tab{
          flex-grow: 1;
          max-height: 40px;
        }
      
        .panel {
          background-color: transparent;
          padding: 20px;
          display: none;
          width: 100%;
          flex-basis: auto;
      }
    }

    .tab {
      display: inline-block;
      padding: 10px;
      vertical-align: top;
      cursor: hand;
      cursor: pointer;
      border-left: 10px solid #ccc;
      
        &:hover{
          background-color: #7f8ff4;
        }
    }  
}

#tab-one:checked ~ .tabs #tab-one-label,
#tab-two:checked ~ .tabs #tab-two-label,
#tab-three:checked ~ .tabs #tab-three-label,
#tab-four:checked ~ .tabs #tab-four-label{
    cursor: default;
    border-left-color: #69be28;
}

#tab-one:checked ~ .tabs #tab-one-panel,
#tab-two:checked ~ .tabs #tab-two-panel,
#tab-three:checked ~ .tabs #tab-three-panel,
#tab-four:checked ~ .tabs #tab-four-panel{
    display: block;
}

@media (max-width: 600px){
  .flex-tabs{
    flex-direction: column;
    
    .tab{
      border-bottom: 1px solid #ccc;
      
        &:last-of-type{
          border-bottom: none;
        }
    }
    
    #tab-one-label{order:1;}
    #tab-two-label{order: 3;}
    #tab-three-label{order: 5;};
    #tab-four-label{order: 7;};
    #tab-one-panel{order: 2;}
    #tab-two-panel{order: 4;}
    #tab-three-panel{order: 6;}
    #tab-four-panel{ order: 8;}
  }
  
    #tab-one:checked ~ .tabs #tab-one-label,
    #tab-two:checked ~ .tabs #tab-two-label,
    #tab-three:checked ~ .tabs #tab-three-label,
    #tab-four:checked ~ .tabs #tab-four-label{
      border-bottom: none;
    }
  
  #tab-one:checked ~ .tabs #tab-one-panel,
  #tab-two:checked ~ .tabs #tab-two-panel,
  #tab-three:checked ~ .tabs #tab-three-panel,
  #tab-four:checked ~ .tabs #tab-four-panel{
    border-bottom: 1px solid #ccc;
  }
}



</style>
