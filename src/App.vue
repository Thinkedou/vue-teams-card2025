<script setup>
  import {ref} from 'vue'
  import MemberCard from './components/MemberCard.vue'
  import { TEAMS } from './assets/js/teamsApp';

  const localMember = ref(TEAMS)

console.log(localMember)
</script>

<template>
  <MemberCard 
    v-for="member in localMember"
    :key="member.profilePic"
    :member="member"
  />
</template>

<style scoped>
</style>
