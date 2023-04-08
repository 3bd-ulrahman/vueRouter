<template>
  <div>
    <h1>
      Contact info
    </h1>
    <p>{{ car.contact.dealer }}</p>
    <p>{{ car.contact.number }}</p>
  </div>
</template>

<script setup>
import { useRoute, RouterView } from 'vue-router';
import cars from '../data/cars.json';

const route = useRoute();
const car = cars.find(car => {
  return car.id === parseInt(route.params.id)
});
</script>
