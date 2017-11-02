<template>
  <main class="">
    <hero color="info" title="That's Zero"></hero>
    <br>
    <tiles/>
  </main>
</template>

<script>
  import Hero from './Hero'
  import Tiles from './Tile'

  export default {
    components: {
      'hero': Hero,
      'tiles': Tiles
    }
  }
</script>