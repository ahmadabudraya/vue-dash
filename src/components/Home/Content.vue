<template>
  <div class="my-5 grid grid-cols-1 gap-5 sm:grid-cols-3">
    <template v-for="item in MockData" :key="item.id">
      <StatsItems v-if="item.type == 'Numeric'" :data="item"/>
      <Progress v-if="item.type == 'Progress'" :data="item"/>
      <LineChart v-if="item.type == 'LineChart'" :data="item"/>
      <PieChart v-if="item.type == 'PieChart'" :data="item"/>
      <TableChart v-if="item.type == 'Table'" :data="item"/>
      <RadialBarChart v-if="item.type == 'RedialBarChart'" :data="item"/>
    </template>
  </div>
</template>

<script>
import StatsItems from "./StatsItems";
import Progress from "./Progress";
import PieChart from "./PieChart";
import LineChart from "./LineChart";
import RadialBarChart from "./RadialBarChart";
import TableChart from "./TableChart";
import MockData from "../../assets/data/mockData.json";

export default{
  name:"Content",
  data:()=>{
    return{
      MockData
    }
  },
  components:{
    StatsItems, 
    Progress,
    PieChart,
    LineChart,
    RadialBarChart,
    TableChart
  }
}
</script>