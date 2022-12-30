<template>
  <vue-countdown :time="interval" v-slot="{ days, hours, minutes, seconds }">
    <div class="flex items-center space-x-3 text-2xl">
      <div class="flex items-center rounded-md border px-4 py-2">
        <span class="text-4xl mr-2">{{ days }}</span>
        <span v-if="days > 1">days</span>
        <span v-else>day</span>
      </div>
      <div class="mx-3">:</div>
      <div class="rounded-md border border- px-4 py-2">
        <span class="text-4xl">{{ hours }}</span>
      </div>
      <div class="mx-3">:</div>
      <div class="rounded-md border border- px-4 py-2">
        <span class="text-4xl">{{ minutes }}</span>
      </div>
      <div class="mx-3">:</div>
      <div class="rounded-md border border- px-4 py-2">
        <span class="text-4xl">{{ seconds }}</span>
      </div>
    </div>
  </vue-countdown>
</template>

<script setup>
import VueCountdown from "@chenfengyuan/vue-countdown";

// eslint-disable-next-line no-undef
const props = defineProps({
  date: {
    type: Date,
    required: true,
  },
});

const interval = props.date - new Date();
</script>
