<template>
  <div class="grid lg:grid-cols-2 gap-10">
    <div class="flex flex-col justify-center text-left">
      <h1 class="text-6xl text-[#f8ffe5] font-bold leading-tight">
        Ramadan is Coming!
      </h1>
      <p class="mt-5 w-2/3">
        Prepare your best for the holy month of Ramadan. Schedule your daily
        prayers, read the Quran, and track your fasting.
      </p>
      <div class="mt-10">
        <dynamic-countdown :date="date" />
      </div>
      <div class="mt-10">
        <button class="bg-[#f8ffe5] text-[#071f36] px-6 py-3 rounded-md">
          Get Started
        </button>
      </div>
    </div>
    <div class="hidden lg:flex items-center justify-end">
      <div
        class="h-full w-2/3 bg-right bg-contain bg-no-repeat"
        :style="{
          backgroundImage:
            'url(' + require('@/assets/img/hilal-masjid-and-clouds.webp') + ')',
        }"
      ></div>
    </div>
  </div>
</template>

<script>
import DynamicCountdown from "@/components/DynamicCountdown";
export default {
  name: "HomeView",
  components: { DynamicCountdown },
  setup() {
    const date = new Date("2023-03-22T17:49:00.000+07:00");
    return { date };
  },
};
</script>
