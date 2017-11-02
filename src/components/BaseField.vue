<template>
  <div class="field">
    <label class="label">{{labelTitle}}</label>
    <p class="control has-icons-left has-icons-right">
      <input :type="type"
        class="input" 
        :placeholder="placeholder"
        :value="inputValue"
        @input="getInput"
        :name="name"
        >
      <span class="icon is-small is-left">
        <i class="fa" :class="iconLeft"> </i>
      </span>
      <span class="icon is-small is-right">
        <i class="fa" :class="iconRight"> </i>
      </span>
    </p>
    <p class="help is-danger" v-if="status === false">{{warning}}</p>
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
    status,
    index: Number,
    warning: String,
    name: String
  },
  methods: {
    getInput(event) {
      this.inputValue = event.target.value
      this.$emit('showInput', this.inputValue, this.index)
    }
  },
  data() {
    return {
      inputValue: ''
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
