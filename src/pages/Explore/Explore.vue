<template lang="html">
  <div class="discover">
    <zhihunavbar></zhihunavbar>
    <div class="row">
      <div class="col-md-2"></div>
      <div class="col-md-8">
        <recommend></recommend>
      </div>
      <div class="col-md-2"></div>
    </div>
  </div>
</template>

<script>
import zhihunavbar from '../commons/ZhihuNavbar'
import recommend from './Recommend'
export default {
  data () {
    return {}
  },
  components: {
    zhihunavbar,
    recommend
  }
}
</script>

<style lang="css">
</style>
