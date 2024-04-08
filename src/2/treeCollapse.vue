<template>
  <div>
    <div class="collapse-wrapper">
      <ul v-for="item in treeItems" :key="item.id" class="collapse-items">
        <li class="collapse-item__title" :id="item.id" @click="toggleItem">
          <span v-if="item.children">
            <i :class="{ rotate: isHidden }" class="fa-solid fa-chevron-right"></i>
          </span>
          <span>{{ item.title }}</span>
        </li>
        <li v-if="isHidden">
          <TreeCollapse v-if="item.children" :treeItems="item.children" />
        </li>
      </ul>
    </div>
  </div>
</template>
<script setup>
import { defineProps, ref } from "vue";
let isHidden = ref(false);
const { treeItems } = defineProps({
  treeItems: {
    type: Array,
    default: () => [],
  },
});

const toggleItem = () => {
  isHidden.value = !isHidden.value;
};
</script>
<style>
@import url(https://fonts.googleapis.com/css2?family=Montserrat:wght@100;200;300;400;500;600;800;900&display=swap);

* {
  font-family: "Montserrat", sans-serif;
  margin: 0;
  padding: 0;
  list-style-type: none;
}
.collapse-items {
  padding-left: 20px;
  display: flex;
  flex-direction: column;
  gap: 5px;
}
.rotate {
  transform: rotate(90deg);
}
.collapse-item__title {
  display: flex;
  gap: 5px;
  transition: all 0.2s;
  cursor: pointer;
  padding: 5px;
  border-left: 4px solid transparent;
}
.collapse-item__title:hover {
  background-color: #d4d4d8;
  font-weight: 500;
  border-color: blue;
}

.collapse-wrapper {
  background-color: #e4e4e7;
}
</style>