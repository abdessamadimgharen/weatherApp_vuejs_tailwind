<template>
    <div
      class="flex py-6 px-5 bg-weather-secondary rounded-md shadow-md cursor-pointer"
    >
      <div class="flex flex-col flex-1">
        <h2 class="text-3xl">{{ city.city }}</h2>
        <h3>{{ city.state }}</h3>
      </div>
  
      <div class="flex flex-col gap-2">
        <p class="text-3xl self-end">
          {{ formatTemperature(city.weather.main.temp) }}
        </p>
        <div class="flex gap-2">
          <span class="text-xs">
            L: {{ formatTemperature(city.weather.main.temp_min) }}
          </span>
          <span class="text-xs">
            H: {{ formatTemperature(city.weather.main.temp_max) }}
          </span>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  defineProps({
    city: {
      type: Object,
      default: () => {},
    },
  });
  
  const formatTemperature = (temperature) => {
    return `${Math.round(temperature)}°C`;
  };
  </script>
  