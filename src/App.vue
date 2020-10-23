<template>
  <div id="app">
    <h1>Vue piano</h1>
    <!--<v-header></v-header>-->
    <v-piano></v-piano>
  </div>
</template>

<script>
import VPiano from '@/components/VPiano'

export default {
  name: 'App',
  components: {
    VPiano
  }
}
</script>

<style>
    h1 {
      text-align: center; 
      text-decoration: blue;
    }
</style>