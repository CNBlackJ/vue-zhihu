<template lang="html">
  <div class="discover">
    <zhihunavbar></zhihunavbar>
    <div class="row">
      <div class="col-md-2"></div>
      <div class="col-md-8">
        <recommend></recommend>
        <hot></hot>
      </div>
      <div class="col-md-2"></div>
    </div>
  </div>
</template>

<script>
import zhihunavbar from '../commons/ZhihuNavbar'
import recommend from './Recommend'
import hot from './Hot'
export default {
  data () {
    return {}
  },
  components: {
    zhihunavbar,
    recommend,
    hot
  }
}
</script>

<style lang="css">
</style>
