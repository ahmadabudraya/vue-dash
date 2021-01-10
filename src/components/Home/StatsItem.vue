<template>
  <div v-if="fetched" :class="`bg-white overflow-hidden shadow rounded-sm order-${item.order}`">
    <div class="px-2 py-3 sm:p-3">
      <div>
        <dt class="text-base font-bold truncate border-gray-200 border-b">
          {{item.title}} <span class="text-gray-500 text-xs font-medium">(50)</span>
        </dt>
        
        <dd class="mt-1 text-2xl font-semibold text-gray-900">
          ${{item.price}}
        </dd>
      </div>
      <div class="flex items-center justify-between mt-8">
        <div class="flex">
          <div>
            <svg class="text-green-900 h-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M14.707 12.707a1 1 0 01-1.414 0L10 9.414l-3.293 3.293a1 1 0 01-1.414-1.414l4-4a1 1 0 011.414 0l4 4a1 1 0 010 1.414z" clip-rule="evenodd" />
            </svg>
          </div>
          <span class="text-xs">({{item.inc}}%)</span>
        </div>
        <div class="text-xs">(${{item.total}})</div>
      </div>
    </div>
  </div>
</template>

<script>
export default{
  name:'StatsItem',
  props:["item"],
  data:()=>{
    return {
      fetched:false
    }
  },
  mounted(){
    setTimeout(()=>{
      this.fetched = true;
    },this.item.order*1000);
  }
}
</script>