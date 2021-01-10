<template>
  <div class="bg-white shadow-sm my-3 p-3 md:flex items-center justify-between">
    <h2 class="font-bold text-lg sm:text-center sm:my-2">Welcome Tim Collins!</h2>
    <div class="">
      <div class="grid grid-cols-1 gap-2 md:grid-cols-2 lg:grid-cols-4">
        <Input :label="`Customer`" />      
        <Input :label="`Inventory`" />      
        <Input :label="`Ticket #`" />      
        <Input :label="`inventory`" />      
      </div>
    </div>
  </div>
</template>

<script>
import Input from "@/components/Global/Input.vue";
export default{
  name:'WelcomeFilter',
  components:{
    Input
  }
}
</script>