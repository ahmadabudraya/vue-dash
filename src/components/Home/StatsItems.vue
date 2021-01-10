<template>
  <div v-if="fetched" :class="`col-span-2 order-${data.order}`">
    <dl class="mb-5 grid grid-cols-1 gap-5 sm:grid-cols-2">
      <template v-for="item in data.items" :key="item.id">
        <StatsItem :item="item"/>
      </template>
    </dl>
  </div>
</template>

<script>

import StatsItem from "./StatsItem";

export default{
  name:"StatsItems",
  components:{
    StatsItem
  },
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