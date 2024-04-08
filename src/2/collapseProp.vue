<template>
  <div class="container">
    <div class="box">
      <TreeCollapse :treeItems="treeLists" />
    </div>
  </div>
</template>

<script setup>
import TreeCollapse from "./treeCollapse.vue";
import { reactive } from "vue";
const treeLists = reactive([
  {
    id: 1,
    title: "Models",
    children: [
      {
        id: 2,
        title: "Data warehouse",
        children: [
          {
            id: 3,
            title: "Report Samples",

          },
          {
            id: 4,
            title: "Sales performance",
          },
        ],
      },
    ],
  },
  {
    id: 5,
    title: "Statistics",
    children: [
      {
        id: 6,
        title: "Lorem Ipsum",
      },
    ],
  },
]);
</script>