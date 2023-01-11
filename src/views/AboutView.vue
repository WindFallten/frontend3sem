<template>
  <AboutComp />
</template>

<script>
import { defineComponent } from 'vue';
import AboutComp from '../components/About.vue';

export default defineComponent({
  name: 'AboutView',
  components: {
    AboutComp,
  },
  
});
</script>