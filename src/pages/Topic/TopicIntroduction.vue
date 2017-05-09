<template lang="html">
  <div class="topic-introduction">
    <div class="pull-left">
      <a href="#">
        <img class="item-img" src="https://pic1.zhimg.com/3f30afdfc_m.jpg" alt="">
      </a>
      <a href="#">
        <span class="item-name">阅读</span>
      </a>
    </div>
    <div class="pull-right">
      <a href="/#/topic#热门排序" v-on:click="isHot()">
        <span v-bind:class="{ 'topic-index-choose': current }">热门排序</span>
      </a>
      <span>|</span>
      <a href="/#/topic#时间排序" v-on:click="isHot()">
        <span v-bind:class="{ 'topic-index-choose': !current }">时间排序</span>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      current: true
    }
  },
  methods: {
    isHot: function () {
      this.current = !this.current
    }
  }
}
</script>

<style lang="css">
  .item-name {
    color: #555;
    font-size: 14px;
    font-weight: 700;
  }
  .topic-introduction {
    padding-bottom: 30px;
  }
  .topic-introduction .pull-right {
    font-size: 12px;
  }
  .topic-index-choose {
    color: #999;
    cursor: text;
  }
</style>
