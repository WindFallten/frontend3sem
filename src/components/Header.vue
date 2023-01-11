<template>
    <header>
        <a href=""><v-img src="../assets/logo.png" alt="logo" width="100px"></v-img></a>
        <ul>
            <v-row justify="center" no-gutters>
            <li>
                <router-link
                class="no-underline cursor-pointer"
                to="/"
                >
                <v-btn
                    variant="text"
                    class="mx-2"
                    rounded="xl"
                >
                    Главная
                </v-btn>
                </router-link>
            </li>
            <li>
                <router-link
                class="no-underline cursor-pointer"
                to="/about"
                >
                <v-btn
                    variant="text"
                    class="mx-2"
                    rounded="xl"
                >
                    О нас
                </v-btn>
                </router-link>
            </li>
            </v-row>
        </ul>
        <v-menu v-model="menu" location="end" :close-on-content-click="false">
            <template v-slot:activator="{ props }">
                <v-btn color="indigo" v-bind="props">
                    Меню
                </v-btn>
            </template>
            <v-card min-width="300">
                <v-list>
                    <v-list-item prepend-avatar="https://cdn.vuetifyjs.com/images/john.jpg" title="Сигалев Георгий"
                        subtitle="Группа:211-323">
                        <template v-slot:append>
                            <v-btn variant="text" :class="fav ? 'text-red' : ''" icon="mdi-heart"
                                @click="fav = !fav"></v-btn>
                        </template>
                    </v-list-item>
                </v-list>

                <v-divider></v-divider>

                <v-list>
                    <v-list-item>
                        <v-switch v-model="message" color="purple" label="Enable messages" hide-details></v-switch>
                    </v-list-item>

                    <v-list-item>
                        <v-switch v-model="hints" color="purple" label="Enable hints" hide-details></v-switch>
                    </v-list-item>
                </v-list>

                <v-card-actions>
                    <v-spacer></v-spacer>

                    <v-btn variant="text" @click="menu = false">
                        Cancel
                    </v-btn>
                    <v-btn color="primary" variant="text" @click="menu = false">
                        Save
                    </v-btn>
                </v-card-actions>
            </v-card>
        </v-menu>
    </header>
</template>

<script>
export default {
    name: 'HeaderComp',
    data: () => ({
        fav: true,
        menu: false,
        message: false,
        hints: true,
        links: [
        'Home',
        'About Us',
        'Team',
        'Services',
        'Blog',
        'Contact Us',
        ],
    })
}

</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    header{
        display: flex;
        
        align-items: center;
        margin: 0px 5px ;
    }
    header ul li{
        text-decoration: none;
    }
</style>
