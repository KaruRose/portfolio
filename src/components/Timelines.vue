<template>
  <div class="timeline mt-5">
    <h5 class="text-h5 text-uppercase text-center text-deep-purple-accent-1">Education & work</h5>
    <v-timeline class="mt-5">
      <v-timeline-item v-for="timeline in timelines" :key="timeline.id" :dot-color="timeline.color"
                       :icon="timeline.icon" size="large">
        <template v-slot:opposite>
          <div :class="`pt-1 headline font-weight-bold text-button text-${timeline.color}`"
               v-text="timeline.period"></div>
        </template>
        <div>
          <h2 :class="`mt-n1 headline font-weight-light mb-1 text-${timeline.color}`">{{ timeline.title }}</h2>
          <h3 :class="`mt-n1 headline font-weight-light mb-4 text-${timeline.color}`">{{ timeline.typeJob }}</h3>
          <h5 :class="`text-button text-${timeline.color}`">{{ timeline.position }}</h5>
          <span class="text-subtitle-2">{{ timeline.description }}</span>
        </div>
      </v-timeline-item>
    </v-timeline>
  </div>
</template>

<script setup>
import { defineComponent, reactive } from 'vue';

defineComponent({
  name: 'Timelines'
})

const timelines = reactive([
  {
    id: 0,
    icon: 'mdi-book-education',
    color: 'cyan lighten-1',
    title: 'Liceo Francisco Javier Pulgar',
    period: 'MAR 2014 — SEP 2019',
  },
  {
    id: 1,
    icon: 'mdi-book-education',
    color: 'blue-grey',
    title: 'Universidad Territorial del estado Merida',
    position: 'in progress',
    period: '2024',
  },
  {
    id: 2,
    icon: 'mdi-briefcase-variant',
    color: 'blue-darken-3',
    title: 'RosasStore',
    typeJob: 'Freelance',
    position: 'front-end',
    period: 'JUN 2024 — JUL 2024',
    description: 'Ñº¡MI'
  },
  // {
  //   id: 3,
  //   icon: 'mdi-briefcase-variant',
  //   color: 'blue-grey',
  //   title: 'Moonion',
  //   position: 'PHP Back-end developer',
  //   period: 'JUN — SEP 2022',
  //   description: 'API integration to e-commerce based on PHP yii2 framework'
  // },
  // {
  //   id: 4,
  //   icon: 'mdi-briefcase-variant',
  //   color: 'deep-orange-lighten-1',
  //   title: 'TuneLab',
  //   position: 'Full-stack developer',
  //   period: 'DEC 2022 — NOWADAYS',
  //   description: 'Developing finTech application from scratch with Laravel 9, Vue.js 3 and Inertia.js'
  // },
])
</script>