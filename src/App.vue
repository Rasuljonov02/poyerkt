<template>
  <div class="wrapper">
    <TableProps />
				<CollapseProp/>
  </div>
</template>

<script setup>
import TableProps from "./components/treevol.vue";
import CollapseProp from "./2/collapseProp.vue";

</script>

<style scoped>
.wrapper {
  width: 1000px;
  margin: 200px auto;
}
</style>