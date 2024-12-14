<script setup>
import {ref} from 'vue'

const data = [
{id : 0, title: 'This is first'},
 {id : 1, title: 'This is second'},
 {id : 2, title: 'This is third'}]
const list = ref(null)

const fetchData = async() => {
  await new Promise(resolve => setTimeout(resolve,3000))
  list.value = data;
}
await fetchData();

    
</script>

<template>
  <div class="container">
    <ul>
      <li v-for="item in list" :key="item.id">{{item.title}}</li>
    </ul>
  </div>
</template>