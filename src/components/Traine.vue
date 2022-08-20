<template>
<v-container>
  <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
    <v-text-field
      v-model="name"
      :rules="nameRules"
      label="Nome do exercício"
      required
    ></v-text-field>

    <v-text-field
      v-model="qtda"
      label="Quantidade de repetições"
    ></v-text-field>

    <v-text-field
      v-model="carga"
      label="Carga"
    ></v-text-field>

    <v-text-field
      v-model="outrasInformacoes"
      label="Outras informações"
    ></v-text-field>

    <v-select
      v-model="select"
      :items="items"
      :rules="[v => !!v || 'Item is required']"
      label="Categoria"
      required
    ></v-select>

    <v-file-input
      multiple 
      show-size   
      truncate-length="15"
    ></v-file-input>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Salvar
    </v-btn>
  </v-form>
</v-container>
</template>

<script>
  export default {
    data: () => ({
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Informe o nome',
      ],
      select: null,
      items: [
        'Inferior',
        'Superior',
        'Cardio',
      ],
    }),

    methods: {
      validate () {
        this.$refs.form.validate()
      },
    //   reset () {
    //     this.$refs.form.reset()
    //   },
    //   resetValidation () {
    //     this.$refs.form.resetValidation()
    //   },
    },
  }
</script>

<style>

</style>