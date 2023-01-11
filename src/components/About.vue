<template>
    <main>
      
        <v-img src="../assets/dell.jpg" alt="logo" height="600px" cover>
            
        </v-img>

    </main>
</template>
  
<script>
  
  export default {
    name: 'AboutComp',
  
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
      async validate () {
        const { valid } = await this.$refs.form.validate()
  
        if (valid) alert('Form is valid')
      },
      reset () {
        this.$refs.form.reset()
      },
      resetValidation () {
        this.$refs.form.resetValidation()
      },
    },
  }
</script>
  
<style scoped>
    .form{
      margin: 5% 25%;
    }
    form h2{
      margin: 1% 0%;
    }
</style>
  