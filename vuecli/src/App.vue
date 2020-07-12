<template>
  <div class="container">
    <Contador/>
  </div>
</template>

<script>
  import Contador from "@/components/Contador";

export default {
  name: 'App',
  components: {
    Contador
  }
}
</script>

<style>
  @import "../node_modules/bootstrap/dist/css/bootstrap.min.css";
</style>
