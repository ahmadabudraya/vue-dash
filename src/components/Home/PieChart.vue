<template>
	<div v-if="fetched" :class="`bg-white overflow-hidden shadow rounded p-5 order-${data.order}`">
		<div class="flex flex-col">
			<h2 class="uppercase font-bold text-base mb-3">how did you hear about us?</h2>
			<div class="flex space-x-2 border-gray-200 border-b pb-2">
				<span class="inline-flex items-center uppercase px-3 py-0.5 rounded-full text-xs font-medium bg-blue-500 text-white">
					Last WEEK
				</span>
				<span class="uppercase text-xs">last two month</span>
				<span class="uppercase text-xs">last month</span>
			</div>
			<apexchart
				width="350"
				type="pie"
				:options="{...chartOptions, labels: data.labels}" 
				:series="data.series"
			/>

		</div>
	</div>
</template>

<script>
import VueApexCharts from "vue3-apexcharts";

export default{
  name:'PieChart',
  props:["data"],
	components:{
		apexchart: VueApexCharts,
	},
	data:()=>{
		return{
      fetched:false,
			chartOptions: {
				chart: {
					width: 380,
					type: 'pie',
				},
				labels: [],
				responsive: [{
					breakpoint: 480,
					options: {
						chart: {
							width: 200
						},
						legend: {
							position: 'bottom'
						}
					}
				}]
			},
		}
	},
  mounted(){
    setTimeout(()=>{
      this.fetched = true;
    },this.data.order*1000);
  }
}
</script>