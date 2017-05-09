<template lang="html">
  <div class="topic">
    <zhihunavbar></zhihunavbar>
    <div class="row main-body">
      <div class="col-md-2"></div>
      <div class="col-md-8">
        <like-topic></like-topic>
        <content-section :isHome="isHome"></content-section>
      </div>
      <div class="col-md-2"></div>
    </div>
  </div>
</template>

<script>
import zhihunavbar from '../commons/ZhihuNavbar'
import contentSection from '../commons/Content'
import likeTopic from './LikeTopic'
export default {
  data () {
    return {
      isHome: false
    }
  },
  components: {
    zhihunavbar,
    contentSection,
    likeTopic
  }
}
</script>

<style lang="css">
  .topic-introduction {
    overflow: hidden;
  }
  .item-img {
    width: 40px;
    height: 40px;
    margin-right: 16px;
    border-radius: 4px;
  }
</style>
