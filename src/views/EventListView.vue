<script setup>
import {ref,onMounted} from 'vue'
import EventCard from '@/components/EventCard.vue';
import EventService from '../services/EventService.js'
const events=ref(null)
onMounted(() => {
  EventService.getEvents()
    .then((response) => {
      events.value = response.data
    })
    .catch((error) => {
      console.log(error)
    })
})
</script>

<template>
  <h1 class="text-2xl font-bold">Event For Good</h1>
  <div class="flex flex-col items-center justify-center">
    <EventCard 
    v-for="event in events" :key="event.id"
    :event="event"
    />
  </div>
</template>
