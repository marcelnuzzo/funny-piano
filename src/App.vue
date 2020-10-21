<template>
  <div id="app">
    <h1>Vue piano</h1>
    <v-header></v-header>
  </div>
</template>

<script>
import VHeader from '@/components/VHeader'
export default {
  name: 'App',
  components: {
    VHeader
  }
}
</script>

<style>
    h1 {
      text-align: center; 
      text-decoration: blue;
    }
</style>