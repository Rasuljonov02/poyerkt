
<template>
  <div>
    <Table :users="users" />
  </div>
</template>

<script setup>
import Table from "./table.vue";
const users = [
  {
    id: 1,
    name: "John Brown",
    age: 32,
    address: "New York No 1 Lake Park",
    status: "nice",
    job: "developer",
  },
  {
    id: 2,
    name: "Jim Green",
    age: 42,
    address: "New York No 1 Lake Park",
    status: "loser",
    job: "",
  },
  {
    id: 1,
    name: "Joe Black",
    age: 32,
    address: "New York No 1 Lake Park",
    status: "cool",
    job: "teacher",
  },
];
</script>

<style scoped></style>
