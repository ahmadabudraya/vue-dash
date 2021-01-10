<template>
	<div v-if="fetched" :class="`bg-white overflow-hidden shadow rounded col-span-2 p-5 order-${data.order}`">
		<div class="flex flex-col">
			<div class="flex justify-between items-center border-gray-200 border-b mb-1">
        <h2 class="font-bold uppercase pb-1">{{data.title}}</h2>
      </div>
      <div class="flex justify-between items-center mb-3">
        <div class="text-gray-400">06 Aug to 12 Aug</div>
        <div class="flex space-x-4">
          <span class="inline-flex items-center uppercase px-3 py-0.5 rounded-full text-sm font-medium bg-blue-500 text-white">
            Last WEEK
          </span>
          <span class="uppercase text-sm">last two month</span>
          <span class="uppercase text-sm">last month</span>
        </div>
      </div>
			<apexchart
				width="100%"
				type="line"
				:options="{...chartOptions, xaxis:{categories:data.categories}}" 
				:series="data.series"
			/>
      <div class="grid gap-3 mt-3 grid-cols-1 sm:grid-cols-2 md:grid-cols-3">
        <div class="text-center">
          <div class="uppercase">number of invoices</div>
          <b>{{data.numberOfInvoices}}</b>
        </div>
        <div class="text-center">
          <div class="uppercase">sales</div>
          <b>${{data.sales}}</b>
        </div>
        <div class="text-center">
          <div class="uppercase">COGS</div>
          <b>${{data.cogs}}</b>
        </div>
      </div>
		</div>
	</div>
</template>

<script>
import VueApexCharts from "vue3-apexcharts";

export default{
  name:'LineChart',
  props:["data"],
	components:{
		apexchart: VueApexCharts,
	},
	data:()=>{
		return{
      fetched:false,
      chartOptions: {
        chart: {
          height: 350,
          type: 'line',
          zoom: {
            enabled: false
          }
        },
        dataLabels: {
          enabled: false
        },
        stroke: {
          curve: 'straight'
        },
        title: {
          text: 'Product Trends by Month',
          align: 'left'
        },
        grid: {
          row: {
            colors: ['#f3f3f3', 'transparent'], // takes an array which will be repeated on columns
            opacity: 0.5
          },
        },
        xaxis: {
          categories: [],
        }
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