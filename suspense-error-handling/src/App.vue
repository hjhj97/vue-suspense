<script setup>
import { defineAsyncComponent } from 'vue';
import Skeleton from './Skeleton.vue'
import Error from './Error.vue'

// const AsyncComponent = defineAsyncComponent(() => import('./AsyncList.vue'))
const AsyncComponent = defineAsyncComponent({
  loader : () => {
    return new Promise((resolve,reject) => setTimeout(() => reject('Error'), 2000))
    },
  errorComponent : Error,
  onError :  (error, retry, fail, attempts) => {
    console.error(`error, ${attempts} times`)
    if(attempts < 3){
      // 최대 3번까지 재시도
      retry()
    } else fail();
    
  }
})
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
