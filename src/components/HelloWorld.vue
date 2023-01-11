<template>
  <main>

    <v-img src="../assets/dell.jpg" alt="logo" height="600px" class="imageback" cover>
      <v-card title="Собеседования - Легко!"
        text="Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempore odit dolore quos fugit, eveniet debitis dignissimos ullam quidem iusto tempora aut architecto, sequi dicta fuga natus voluptate non sapiente omnis!"
        class="jumbo">
        <v-card-actions>
          <v-btn color="success" size="small">Click me</v-btn>
        </v-card-actions>
      </v-card>
    </v-img>
    <v-form class="form" ref="form" v-model="valid" lazy-validation>
      <h2 class="text-h2">Заполните анкету</h2>
      <v-text-field v-model="name" :counter="10" :rules="nameRules" label="Имя" required></v-text-field>

      <v-text-field v-model="email" :rules="emailRules" label="Почта" required></v-text-field>

      <v-select v-model="select" :items="items" :rules="[v => !!v || 'Выберите один из вариантов']"
        label="Выберите вариант" required></v-select>

      <v-checkbox v-model="checkbox" :rules="[v => !!v || 'Вы должны подтвердить своё согласие!']" label="Вы согласны?"
        required></v-checkbox>

      <v-btn color="success" class="mr-4" @click="validate">
        Отправить заявку
      </v-btn>

      <v-btn color="" class="mr-4" @click="reset">
        Очистить форму
      </v-btn>
    </v-form>
  </main>
</template>

<script>

export default {
  name: 'HelloWorld',

  data: () => ({
    valid: true,
    name: '',
    nameRules: [
      v => !!v || 'Заполните поле "Имя"',
      v => (v && v.length <= 10) || 'Имя не должно быть больше 10 букв',
    ],
    email: '',
    emailRules: [
      v => !!v || 'Впишите почту',
      v => /.+@.+\..+/.test(v) || 'Проверте написание почты',
    ],
    select: null,
    items: [
      'Работодатель',
      'В поисках работы',
    ],
    checkbox: false,
  }),

  methods: {
    async validate() {
      const { valid } = await this.$refs.form.validate()

      if (valid) alert('Form is valid')
    },
    reset() {
      this.$refs.form.reset()
    },
    resetValidation() {
      this.$refs.form.resetValidation()
    },
  },
}
</script>

<style scoped>
.form {
  margin: 5% 25%;
}

form h2 {
  margin: 1% 0%;
}

.jumbo {
  display: flex;
  flex-wrap: wrap;
  margin: 0% 15%;

  max-width: 40%;
}

.imageback {
  display: flex;

  justify-content: center;
  align-items: center;
}
</style>
