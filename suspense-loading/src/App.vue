<script setup>
import { defineAsyncComponent } from 'vue';

const AsyncComponent = defineAsyncComponent(() => import('./AsyncList.vue'))
</script>

<template>
  <div>
    <h2>Hello!</h2>
    <Suspense>      
      <AsyncComponent />      
      <template #fallback>
        Loading...
      </template>
    </Suspense>
  </div>
</template>
