<script setup>
import CountdownHeader from '@/components/CountdownHeader.vue'
import CountdownSegment from './components/CountdownSegment.vue'
import { useNow } from '@vueuse/core'

const now = useNow()
const christmas = new Date('12/25/2022 00:00:00')
const christmas2 = new Date(christmas.getTime() - 100)
const christmas3 = new Date(christmas - 1000) // subtract 1 sec to christmas date
const christmas4 = new Date('12/24/2022 23:59:59')
</script>
<template>
  <div class="w-full h-full flex justify-center items-center p-10">
    <div>
      <div class="shadow-md relative bg-white p-5 rounded-lg border-gray-100 border-[1px]">
        <CountdownHeader />
        <main class="flex justify-center">
          <CountdownSegment label="days" :number="christmas2.getDate() - now.getDate()" />
          <CountdownSegment label="hours" :number="christmas2.getHours() - now.getHours()" />
          <CountdownSegment label="minutes" :number="christmas2.getMinutes() - now.getMinutes()" />
          <CountdownSegment label="seconds" :number="christmas2.getSeconds() - now.getSeconds()" />
        </main>
        <main class="flex justify-center">
          <CountdownSegment label="days" :number="christmas3.getDate() - now.getDate()" />
          <CountdownSegment label="hours" :number="christmas3.getHours() - now.getHours()" />
          <CountdownSegment label="minutes" :number="christmas3.getMinutes() - now.getMinutes()" />
          <CountdownSegment label="seconds" :number="christmas3.getSeconds() - now.getSeconds()" />
        </main>
        <main class="flex justify-center">
          <CountdownSegment label="days" :number="christmas4.getDate() - now.getDate()" />
          <CountdownSegment label="hours" :number="christmas4.getHours() - now.getHours()" />
          <CountdownSegment label="minutes" :number="christmas4.getMinutes() - now.getMinutes()" />
          <CountdownSegment label="seconds" :number="christmas4.getSeconds() - now.getSeconds()" />
        </main>
      </div>
      <h4 class="mt-10 text-gray-400 text-center text-sm">
        This challenge brought to you by <a href="https://vueschool.io/" class="underline">Vue School</a>
      </h4>
    </div>
  </div>
</template>

<style>
div {
  display: block;
}

body {
  @apply bg-gray-100;
}

.list-enter-active,
.list-leave-active {
  transition: all 0.5s ease;
}
.list-enter-from,
.list-leave-to {
  opacity: 0;
  transform: translateX(30px);
}
</style>
