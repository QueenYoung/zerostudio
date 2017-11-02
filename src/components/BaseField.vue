<template>
  <div class="field">
    <label class="label">{{labelTitle}}</label>
    <p class="control has-icons-left has-icons-right">
      <input :type="type"
        class="input" 
        :placeholder="placeholder"
        :value="email"
        @input="getInput"
        >
      <span class="icon is-small is-left">
        <i class="fa" :class="iconLeft"> </i>
      </span>
      <span class="icon is-small is-right">
        <i class="fa" :class="iconRight"> </i>
      </span>
    </p>
  </div>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      required: true
    },
    placeholder: String,
    iconName: String,
    labelTitle: {
      type: String,
      required: true
    },
    status
  },
  methods: {
    getInput(event) {
      this.email = event.target.value
      this.$emit('showInput', this.email)
    }
  },
  data() {
    return {
      email: ''
    }
  },
  computed: {
    iconLeft() {
      return this.iconName ? `fa-${this.iconName}` : ''
    },
    iconRight() {
      const icons = ['fa-close', 'fa-check']
      return icons[Number(this.status)] || ''
    }
  }
}
</script>
