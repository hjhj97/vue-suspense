<script setup>
import { defineAsyncComponent } from 'vue';
import Skeleton from './Skeleton.vue'

const AsyncComponent = defineAsyncComponent(() => import('./AsyncList.vue'))
</script>

<template>
  <div>
    <h2>Hello!</h2>
    <Suspense>      
      <AsyncComponent />      
      <template #fallback>
        <Skeleton />
      </template>
    </Suspense>
  </div>
</template>
