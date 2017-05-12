<template lang="html">
  <div class="hot row">
    <b-tabs>
      <b-tab title="今日最热" href='/#/explore#今日最热'>
        <content-section class="content-section"></content-section>
      </b-tab>
      <b-tab title="本月最热" href="/#/explore#本月最热">
        <content-section class="content-section"></content-section>
      </b-tab>
    </b-tabs>
  </div>
</template>

<script>
import contentSection from '../commons/Content'
export default {
  data () {
    return {}
  },
  components: {
    contentSection
  }
}
</script>

<style lang="css">
  .hot {
    padding-top: 10px;
  }
  .content-section {
    padding: 10px 0;
  }
</style>
