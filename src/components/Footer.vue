<template>
    <footer>
      <v-footer class="bg-grey-lighten-1">
        <v-row justify="center" no-gutters>
          <router-link
              class="no-underline cursor-pointer"
              to="about"
          >
            <v-btn
              v-for="link in links"
              :key="link"
              color="white"
              variant="text"
              class="mx-2"
              rounded="xl"
            >
              {{ link }}
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
    footer{
        display: flex;
        justify-content: center;
    }
</style>