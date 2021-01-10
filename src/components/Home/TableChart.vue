<template>
  <div v-if="fetched" :class="`bg-white overflow-hidden shadow rounded col-span-2 p-5 order-${data.order}`">
    <Table
      :columns="data.columns"
      :dataSource="data.dataSource"
    />
  </div>

</template>

<script>
import Table from "@/components/Global/Table.vue";

export default{
  name:'TableChart',
  props:["data"],
  components:{
    Table
  },
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