<template lang="html">
  <div class="home">
    <navbar></navbar>
    <div class="row main-body">
      <div class="col-md-2"></div>
      <div class="col-md-8">
        <home-entry></home-entry>
      </div>
      <div class="col-md-2"></div>
    </div>
  </div>
</template>

<script>
import navbar from './Navbar'
import homeEntry from './HomeEntry'

export default {
  data () {
    return {}
  },
  components: {
    navbar,
    homeEntry
  }
}
</script>

<style lang="css">
  .main-body {
    padding-top: 25px;
  }
</style>
