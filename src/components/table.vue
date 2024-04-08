<template>
  <div>
    <table class="users">
      <thead>
        <tr>
          <th>Name</th>
          <th>Age</th>
          <th>Address</th>
          <th>Tags</th>
          <th>Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <td class="name">{{ user.name }}</td>
          <td>{{ user.age }}</td>
          <td>{{ user.address }}</td>
          <td class="status">
            <span
              :class="[
                user.status == 'loser' ? 'status-danger' : 'status-success',
              ]"
              >{{ user.status }}</span
            >
            <span v-if="user.job" class="job"> {{ user.job }}</span>
          </td>
          <td class="table-btns">
            <button>
              <a href="#">Invite - {{ user.name }}</a>
            </button>
            <button class="table-delete__btn">
              <a href="#">Delete</a>
            </button>

            <button>
              <a href="#"
                >More actions
                <svg
                  width="12"
                  aria-hidden="true"
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 10 6"
                >
                  <path
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="m1 1 4 4 4-4"
                  /></svg
              ></a>
            </button>

          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
import { defineProps, ref } from "vue";
let { users } = defineProps({
  users: {
    type: Array,
    required: true,
  },
});
</script>

<style scoped>
@import url(https://fonts.googleapis.com/css2?family=Montserrat:wght@100;200;300;400;500;600;800;900&display=swap);

* {
  font-family: "Montserrat", sans-serif;
  margin: 0;
  padding: 0;
  text-decoration: none;
}
.users {
  border-collapse: collapse;
  width: 100%;
}

.users td,
.users th {
  border: 1px solid #838080;
  padding: 8px;
}

.users tr:nth-child(even) {
  background-color: #f2f2f2;
}

.users tr:hover {
  background-color: #ddd;
}
.name {
  color: blue;
}
.users th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #f2f2f2;
  font-weight: 600;
}
.table-btns {
  display: flex;
  gap: 10px;
  height: 52px;
}
.table-btns .table-delete__btn {
  border-left: 1px solid #e4e4e7;
  border-right: 1px solid #e4e4e7;
  padding: 0 5px;
}
.table-btns button {
  background-color: transparent;
  border: none;
}
.table-btns button a {
  color: blue;
  border: 0;
}
.status-success {
  color: #22c55e;
  background-color: #dcfce7;
  padding: 3px 6px;
  border: 1px solid green;
  margin-right: 5px;
  border-radius: 5px;
  text-transform: uppercase;
  font-size: 12px;
}
.status-danger {
  color: #d21034;
  background-color: #bba4a6;
  padding: 3px 6px;
  border: 1px solid red;
  margin-right: 5px;
  border-radius: 5px;
  text-transform: uppercase;
  font-size: 12px;
}
.job {
  color: #818cf8;
  background-color: #e0e7ff;
  padding: 3px 6px;
  border: 1px solid rgb(25, 25, 132);
  margin-right: 5px;
  border-radius: 5px;
  text-transform: uppercase;
  font-size: 12px;
}
td {
  cursor: pointer;
}
</style>