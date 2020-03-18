<template>
  <div>
    <h1>Event listing</h1>
    <EventCard v-for="event in events" :key="event.id" :event="event" />
    <BaseIcon />
  </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'
import EventService from '@/services/EventService'

export default {
  components: {
    EventCard
  },
  data() {
    return {
      events: []
    }
  },
  async created() {
    try {
      const response = await EventService.getEvents()
      console.log(response)
      this.events = response.data
    } catch (error) {
      console.error(error)
    }
  }
}
</script>

<style scoped></style>
