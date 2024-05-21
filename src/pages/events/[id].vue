<script setup lang="ts">
import { events } from '@/data'
import { useRoute } from 'vue-router/auto'

const props = defineProps<{ id: string }>()
const route = useRoute('/events/[id]')
const event = events.find((event) => event.id === Number(route.params.id))
</script>
<template>
  <div v-if="event">
    <div>
      <header>
        <h1>{{ event.title }}</h1>
        <ul>
          <li>
            <span>Date</span>
            <span>{{ event.date }}</span>
          </li>
          <li>
            <span>Lieux</span>
            <span>{{ event.lieu }}</span>
          </li>
          <li>
            <span>Catégorie</span>
            <span>{{ event.categorie }}</span>
          </li>
        </ul>
      </header>
    </div>
    <p>{{ event?.excerpt }}</p>
    <div v-html="event?.description"></div>
  </div>
  <div v-else>
    <h1>Pas d'évènement correspondant</h1>
  </div>
</template>
