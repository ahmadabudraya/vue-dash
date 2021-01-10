<template>
  <div v-if="fetched" :class="`bg-white overflow-hidden shadow rounded p-5 order-${data.order}`">
    <div class="flex flex-col items-center">
      <img class="w-44 block" :src="`${data.img}`"/>
      <h3 class="font-bold my-3">{{data.title}}</h3>
      <div class="relative w-full h-4 sm:w-1/2 bg-gray-200 rounded">
        <div :style="`width:${data.progress}%`" class="absolute top-0 h-4 overflow-hidden rounded bg-blue-500"></div>
      </div>
      <div class="text-green-600 underline cursor-pointer w-1/2">Complete your profile</div>
    </div>
  </div>
</template>

<script>
export default{
  name:'Progress',
  props:["data"],
  data:()=>{
    return{
      fetched:false
    }
  },
  mounted(){
    setTimeout(()=>{
      this.fetched = true;
    },this.data.order*1000);
  }
}
</script>