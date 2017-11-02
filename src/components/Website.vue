<template>
  <main class="">
    <hero color="info" title="That's Zero"></hero>
    <br>
    <div class="container">
      <tiles/>
      <h2 class="title">加入我们</h2>
      <my-form/>
    </div>
  </main>
</template>

<script>
  import Hero from './Hero'
  import Tiles from './Tile'
  import Form from './my-form'

  export default {
    components: {
      'hero': Hero,
      'tiles': Tiles,
      'my-form': Form
    }
  }
</script>