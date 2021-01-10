<template>
<div>
  <label v-if="label" class="block text-sm font-medium text-gray-700">{{label}}</label>
  <div class="mt-1 relative rounded-md shadow-sm">
    <input type="text" name="account_number" class="focus:ring-indigo-500 focus:border-indigo-500 block w-full pr-10 sm:text-sm border-gray-300 rounded-md" placeholder="Search">
    <div class="absolute inset-y-0 right-0 pr-3 flex items-center pointer-events-none">
     
      <svg class="h-5 w-5 text-gray-400" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 20 20" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
      </svg>
    </div>
  </div>
</div>

</template>

<script>
export default{
    name:'Input',
    props:['label']
}
</script>