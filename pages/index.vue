<template>
  <div class="container">
    <div class="table">
      <Table />
    </div>
  </div>
</template>

<script>
import Table from "../components/Table";
export default {
  components: { Table }
};
</script>

<style>
:root {
  --border: 2px solid #555;
}
.container {
  background: whitesmoke;

  height: 100vh;
  display: flex;

  flex: 1;

  align-items: center;
  justify-content: center;
}
</style>
