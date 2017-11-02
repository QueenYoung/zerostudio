<template>
  <main class="">
    <hero color="info" title="We're coming" subtitle="零点招新"></hero>
    <div class="section">
      <tiles/>
      <hr>
      <h2 class="title">加入我们</h2>
      <my-form/>
    </div>
  </main>
</template>

<script>
  import Hero from './Hero'
  import Tiles from './Tile'
  import Form from './my-form'
  import '../movetriangle'

  export default {
    components: {
      'hero': Hero,
      'tiles': Tiles,
      'my-form': Form
    }
  }
</script>