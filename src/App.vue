<template>
  <v-app :theme="theme">
    <div class="header" >
      <HeaderComp/>
      <v-btn max-width="40px" :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'" @click="onClick"></v-btn>
    </div>
    <v-main class="main">
      <router-view/>
    </v-main>
    <FooterComp></FooterComp>
  </v-app>
</template>

<script>
import HeaderComp from './components/Header.vue';
import FooterComp from './components/Footer.vue';

export default {
  name: 'App',

  data: () => ({
    //
  }),
  components: {
    HeaderComp,
    FooterComp
  },
}
</script>
<script setup>
    import { ref } from 'vue'

    const theme = ref('dark')

    function onClick () {
    theme.value = theme.value === 'light' ? 'dark' : 'light'
    }
</script>
<style>
  .header{
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 1%;
  }
</style>