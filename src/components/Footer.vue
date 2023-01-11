<template>
  <footer>
    <v-footer >
      <v-row justify="center" no-gutters>
        <router-link class="no-underline cursor-pointer" to="/">
          <v-btn variant="text" class="mx-2" rounded="xl">
            Главная
          </v-btn>
        </router-link>

        <router-link class="no-underline cursor-pointer" to="/about">
          <v-btn variant="text" class="mx-2" rounded="xl">
            О нас
          </v-btn>
        </router-link>
        <v-col class="text-center mt-4" cols="12">
          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-col>
      </v-row>
    </v-footer>
  </footer>
</template>

<script>
export default {
  name: 'FooterComp',
  data: () => ({
    links: [
      'Home',
      'About Us',
      'Team',
      'Services',
      'Blog',
      'Contact Us',
    ],
  }),
}
</script>

<style scoped>
footer {
  display: flex;
  justify-content: center;
}
</style>