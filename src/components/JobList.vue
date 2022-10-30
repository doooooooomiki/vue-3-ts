<script setup lang="ts">

import type Job from '@/types/Job'
import type OrderTerm from '@/types/OrderTerm'

defineProps<{
  jobs?: Job[],
  order?: OrderTerm,
}>()

</script>

<template>
  <div class="job-list">
    <p>
      Ordered by {{order}}
    </p>
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2>
          {{job.title}} in {{job.location}}
        </h2>
        <div class="job-salary">
          <p>
            {{job.salary}}$
          </p>
        </div>
        <div class="job-description">
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aperiam, soluta obcaecati praesentium molestiae atque officiis quasi esse voluptate rem iure pariatur natus numquam mollitia voluptatibus, expedita ex quisquam nostrum laboriosam.
        </div>
      </li>
    </ul>
  </div>
</template>

<style scoped>
  .job-list {
    max-width: 960px;
    margin: 40px auto;
  }
  .job-list ul {
    padding: 0;
  }
  .job-list li {
    list-style-type: none;
    background: white;
    padding: 16px;
    margin: 16px 0;
    border-radius: 4px;
  }
  .job-list h2 {
    margin: 0 0 10px;
    text-transform: capitalize;
  }
  .job-salary {
    display: flex;
  }
  .job-salary img {
    width: 30px;
  }
  .job-salary p {
    color: #17bf66;
    font-weight: bold;
    margin: 10px 4px;
  }
</style>