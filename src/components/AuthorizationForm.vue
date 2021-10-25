<template>
  <b-form @submit="onSubmit" @reset="onReset" v-if="show">
    <b-form-group
      id="input-group-1"
      label="Логин"
      label-for="loginAuthInput"
      description="Пользователь не зарегистрирован!"
    >
      <b-form-input
        id="loginAuthInput"
        v-model="form.email"
        type="email"
        placeholder="Введите логин"
        required
      ></b-form-input>
    </b-form-group>
<b-form-group
      id="input-group-1"
      label="Пароль"
      label-for="passwordAuthInput"
      description="Неверно введен пароль!"
    >
      <b-form-input
        id="passwordAuthInput"
        v-model="form.email"
        type="email"
        placeholder="Введите пароль"
        required
      ></b-form-input>
    </b-form-group>
    <b-button type="submit" variant="primary">Submit</b-button>
    <b-button type="reset" variant="danger">Reset</b-button>
  </b-form>
</template>

<script>
  export default {
    data() {
      return {
      form: {
        email: "",
          name: '',
          food: null,
          checked: []
        },
      show: true,
      }
    },
    methods: {
      onSubmit(event) {
        event.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(event) {
        event.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.name = ''
        this.form.food = null
        this.form.checked = []
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>

<style scoped></style>
