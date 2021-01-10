<template>
  <div class="home">
    <WelcomeFilter/>
    <Content/>
  </div>
</template>

<script>
// @ is an alias to /src
import WelcomeFilter from "@/components/Home/WelcomeFilter.vue";
import Content from "@/components/Home/Content";
export default {
  name: "Home",
  components: {
    WelcomeFilter,
    Content
  }
};
</script>
