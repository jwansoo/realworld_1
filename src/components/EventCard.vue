<template>
  <RouterLink 
  class="text-indigo-700"
  :to="{name:'event-details',params:{id:event.id}}">
  <div class="p-5 w-60 cursor-pointer border border-gray-500 mt-4 hover:shadow-xl">
    <h2>{{ event.title }}</h2>
    <span>@{{ event.time }} on {{ event.date }}</span>
  </div>
</RouterLink>
</template>

<script setup>
import {ref} from 'vue'
defineProps({
  event:{type:Object,required:true}
})
</script>

<style lang="scss" scoped>

</style>