<template>
  <div>
    <h1>
      car view
    </h1>
    <p>{{ car.name }}</p>
    <p>{{ car.year }}</p>
    <p>{{ car.price }}</p>
    <button @click="router.push(`/cars/${car.id}/contact`)">Click for contact</button>
    <RouterLink :to="`/cars/${car.id}/contact`">aaa</RouterLink>
    <RouterView />
  </div>
</template>

<script setup>
import { useRoute, useRouter, RouterView } from 'vue-router';
import cars from '../data/cars.json';

const route = useRoute();
const router = useRouter();

const car = cars.find(car => {
  return car.id === parseInt(route.params.id)
});
</script>
