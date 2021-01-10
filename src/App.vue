<template>
  <div id="app">
    <Topbar />
    <div class="m-auto w-11/12 overflow-hidden">
      <router-view />
    </div>
  </div>
</template>


<script>

import Topbar from "@/components/Topbar/Topbar.vue";


export default{
  name:'App',
  components:{
    Topbar
  }
}
</script>

<style lang="scss">
#app{
  background:#F3F4F6
}
</style>
