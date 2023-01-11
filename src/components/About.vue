<template>
  <main>
    <v-card v-for="(post, i) in allPosts" :key="i" class="mx-auto" max-width="344">
      <v-img src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg" height="200px" cover></v-img>

      <v-card-title>
        {{ i+ 1 }}
        {{ post.title }}
      </v-card-title>

      <v-card-subtitle>
        1,000 miles of wonder
      </v-card-subtitle>

      <v-card-actions>
        <v-btn color="orange-lighten-2" variant="text">
          Explore
        </v-btn>

        <v-spacer></v-spacer>

        <v-btn :icon="show ? 'mdi-chevron-up' : 'mdi-chevron-down'" @click="show = !show"></v-btn>
      </v-card-actions>

      <v-expand-transition>
        <div v-show="show">
          <v-divider></v-divider>

          <v-card-text>
            {{ post.text }}
          </v-card-text>
        </div>
      </v-expand-transition>
    </v-card>
    <div>
      <h1>My Weather App</h1>
      <button v-on:click="getWeatherData">Get Weather Data</button>
      <div>{{ weatherDataList }}</div>
    </div>>
  </main>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';

export default {
  name: 'AboutComp',

  data: () => ({
    show: false,
  }),
  methods: mapActions([
    'fetchPosts'
  ]),
  async mounted() {
    this.fetchPosts();
  },
  computed: mapGetters([
    'allPosts'
  ]),
}
</script>

<style scoped>
main{
  display: flex;
  flex-wrap: wrap;
}

form h2 {
  margin: 1% 0%;
}
</style>
