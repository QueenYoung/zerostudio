<template>
  <form @submit.prevent="login">
  <my-field 
    iconName="envelope"
    placeholder="write your email"
    type="email"
    labelTitle="email"
    @showInput="yo"
    :status="status[0]"
  />
  <div class="field">
    <p class="control">
      <button 
        :disabled="!canLogin()"
        class="button is-success"
      >Login</button>
    </p>
  </div>
  </form>
</template>

<script>
  import Field from './BaseField'
  import Hero from './Hero'

  export default {
    components: {
      'my-field': Field,
      'hero': Hero
    },
    data() {
      return {
        status: [undefined],
        emailInput: ''
      }
    },
    methods: {
      yo(input) {
        this.emailInput = input
        this.status.splice(0, 1, input.endsWith('@gmail.com'))
      },
      login() {
        let formData = new FormData()
        formData.append('email', this.emailInput)
        console.log(formData['email'])
      },
      canLogin() {
        return this.status.every(Boolean)
      }
    }
  }
</script>



