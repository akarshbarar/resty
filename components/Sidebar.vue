<template>
  <div class="sidebar">
      <nuxt-link to="/"><div  v-tooltip="restapi" class="sidebar__icon"><font-awesome-icon :icon="['fas', 'wifi']"/></div></nuxt-link>
      <nuxt-link to="/websocket"><div class="sidebar__icon"><font-awesome-icon :icon="['fas', 'rocket']"/></div></nuxt-link>
      <nuxt-link to="/graphql"><div class="sidebar__icon"><font-awesome-icon :icon="['fas', 'project-diagram']"/></div></nuxt-link>
      <nuxt-link to="/documentation"><div class="sidebar__icon"><font-awesome-icon :icon="['fas', 'book']"/></div></nuxt-link>
      <nuxt-link to="/setting"><div class="sidebar__icon"><font-awesome-icon :icon="['fas', 'cog']"/></div></nuxt-link>
      
  </div>
</template>

<script>
export default {

data:{
  restapi:'REST API'
}
}
</script>

<style>
.sidebar{
  width:10%;
  background-color: #0A0A0A;
color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
}

.sidebar__icon{
  width: 50px;
  height: 50px;
  padding: 5px;
  background-color: #6c7ff2;
  border-radius: 10px;
  justify-content: center;
  display: flex;
  align-items: center;
}

.sidebar__icon:hover{
  transform: scale(1.1);
}

</style>