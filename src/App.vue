<script setup lang="ts">

import JobList from '@/components/JobList.vue'
import type OrderTerm from '@/types/OrderTerm'
import type Job from '@/types/Job'
import { ref } from 'vue'

const jobs = ref<Job[]>([
  {
    title: 'farm worker',
    location: 'lon lon ranch',
    salary: 30000,
    id: '1'
  },
  { 
    title: 'quarryman', 
    location: 'death mountain',
    salary: 40000,
    id: '2' 
  },
  { 
    title: 'flute player', 
    location: 'the lost woods', 
    salary: 35000, 
    id: '3' 
  },
  { 
    title: 'fisherman', 
    location: 'lake hylia', 
    salary: 21000, 
    id: '4' 
  },
  { 
    title: 'prison guard', 
    location: 'gerudo valley', 
    salary: 32000, 
    id: '5' 
  }
])

const order = ref<OrderTerm>('title')

const handleClick = (term: OrderTerm) => {
  order.value = term
}

</script>

<template>
  <main>
    <section>
      <div class="order">
        <button @click="handleClick('title')">order by title</button>
        <button @click="handleClick('salary')">order by salary</button>
        <button @click="handleClick('location')">order by location</button>
      </div>
    </section>
    <JobList :jobs="jobs" :order="order" />
  </main>
</template>

<style scoped>
  section {
    text-align: center;
  }
  section .order {
    margin-top: 20px;
  }
</style>