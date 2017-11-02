<template>
  <main class="">
    <hero color="info" title="We're coming" subtitle="零点招新"></hero>
    <div class="section">
      <tiles/>
      <hr>
      <a href="http://bossbang.cc/f/59f9df3ce7aea941a8667b8c" target="_blank" class="button is-primary">加入我们</a>
    </div>
  </main>
</template>

<script>
  import Hero from './Hero'
  import Tiles from './Tile'
  import '../movetriangle'

  export default {
    components: {
      'hero': Hero,
      'tiles': Tiles
    }
  }
</script>