<template>
  <h2>Home</h2>

  <ul>
    <template v-for="(user, index) in users" :key="index">
      <li v-if="user.is_admin"> {{ user.firstName }}</li>
    </template>
  </ul>

  <h2>Not Admin</h2>

  <ul>
    <template v-for="(user, index) in usersIsNotAdmin" :key="index">
      <li> {{ user.firstName }}</li>
    </template>
  </ul>

</template>

<script setup>
import { computed, reactive, ref } from "vue";

const user = reactive({
    firstName: 'Andreew',
    lastName: 'Cardoso',
    is_admin: true
})

const users = reactive([
  {
    firstName:'jenny',
    is_admin:1
  },
  {
    firstName:'Anne',
    is_admin:0
  },
  {
    firstName:'Mary',
    is_admin:1
  },
  {
    firstName:'James',
    is_admin:0
  },
])

const fullName = computed(() => {
  return user.firstName + ' - ' + user.lastName
})

const usersIsNotAdmin = computed(() => {
  return users.filter((user) => user.is_admin == 0)
})
</script>

