<template lang="html">
  <div class="like-topic">
    <div class="row like-topic-head">
      <div class="col-md-12">
        <span class="pull-left like-topic-title">
          <i class="fa fa-list"></i>
          已关注的话题动态
        </span>
        <div class="pull-right">
          <a href="#" class="like-topic-count">共关注26个话题</a>
        </div>
      </div>
    </div>
    <ul class="topic-items">
      <li v-for="(item, index) in topic_items"
          :id="index"
          class="topic-item"
          v-on:click="isChoose(index)" v-bind:class="{ 'current-item': index === isActive }">
        <a class="topic-item-link" :href="'#/topic#' + item">{{item}}</a>
      </li>
    </ul>
    <topic-introduction></topic-introduction>
  </div>
</template>

<script>
import topicIntroduction from './TopicIntroduction'
export default {
  name: 'like-topic',
  data () {
    return {
      isActive: 0,
      topic_items: ['阅读', '生活', '摄影', '运动', '西部世界', 'Vue.js', 'Python', 'Ruby on Rails', '体育', 'life style', 'Andriod', 'Apple', 'Iphone', 'Kindle']
    }
  },
  components: {
    topicIntroduction
  },
  methods: {
    isChoose: function (index) {
      this.isActive = index
    }
  }
}
</script>

<style lang="css">
  .row .like-topic-head {
    border-bottom: 1px solid #ccc;
    margin-left: 0px;
    margin-right: 0px;
    padding-bottom: 8px;
  }
  .like-topic-title {
    font-size: 14px;
    font-weight: 700;
    color: #666;
  }
  .like-topic-count {
    font-size: 12px;
    font-weight: 400;
    color: #999;
  }
  ul li {
    display: inline;
  }
  .topic-items {
    padding: 18px 0 8px;
    border-bottom: 1px solid #eee;
    overflow: hidden;
  }
  .topic-item {
    float: left;
    margin: 0 10px 10px 0;
    list-style: none;
  }
  .topic-item a {
    display: block;
    padding: 2px 10px;
    border-radius: 30px;
    text-decoration: none;
    border: 1px solid #daecf5;
  }
  .current-item a {
    background: #259;
    border-color: #259;
    color: #fff;
  }
  li a:hover {
    background: #259;
    border-color: #259;
    color: #fff;
  }
</style>
