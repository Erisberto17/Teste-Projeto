
<template>
  <main>
    <Nav/>
    <Dashboard />
  </main>
</template>
<script>
  import Nav from "../components/nav.vue";
  import Dashboard from	"../components/DashBoard.vue";

  export default {
    name:"HomeView",
    components:{
      Nav,
      Dashboard
  }
}
</script>