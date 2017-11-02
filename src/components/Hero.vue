<template>
<section class="hero is-medium is-bold" :class="colorClass">
  <div class="hero-body">
    <div class="content container">
      <h1 class="title is-size-1">{{title | capitalized}}</h1>
      <h2 class="subtitle is-size-4">{{subtitle | capitalized}}</h2>
    </div>
  </div>
</section>
</template>

<script>
  export default {
    props: {
      color: {
        type: String,
        required: true
      },
      title: {
        type: String,
        required: true
      },
      subtitle: {
        type: String,
        required: false
      }
    },
    computed: {
      colorClass() {
        return `is-${this.color}`
      }
    },
    filters: {
      capitalized(value) {
        if (!value) return
        return value.split(' ').map(
          word => word.charAt(0).toUpperCase() + word.slice(1)
        ).join(' ')
      }
    }
  }
</script>
