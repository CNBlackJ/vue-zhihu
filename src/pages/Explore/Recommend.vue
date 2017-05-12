<template lang="html">
  <div class="recommend row">
    <div class="col-md-12 recommend-header">
      <div class="pull-left">
        <i class="fa fa-list"></i>
        <span class="recommend-title">
          编辑推荐
        </span>
      </div>
      <div class="pull-right">
        <a href="#">
          <span class="recommend-more">
            更多推荐 »
          </span>
        </a>
      </div>
    </div>

    <div class="col-md-12 recommend-item" v-for="recommend in recommends">
      <div class="pull-left">
        <a href="#">
          <span class="recommend-item-title">{{ recommend.title }}</span>
        </a>
      </div>
      <div class="pull-right">
        <span class="recommend-item-meta">{{ recommend.meta }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      recommends: [
        {
          title: '「十二周入门语言学」第一周·语言学不是学语言（下）',
          meta: '听雨庭院工作室谢喵图书馆'
        },
        {
          title: '多标签（multi-label）数据的学习问题，常用的分类器或者分类策略有哪些？',
          meta: '问答'
        },
        {
          title: '什么改变让美式车不再“美式"了？',
          meta: '问答'
        },
        {
          title: '认知心理学中「表征」的概念是什么？',
          meta: '问答'
        }
      ]
    }
  },
  methods: {
    show: function () {

    }
  }
}
</script>

<style lang="css">
  .recommend .recommend-header {
    color: #666;
    border-bottom: 1px solid #ccc;
    padding: 25px 0 10px 0;
  }
  .recommend-title {
    font-size: 13px;
    font-weight: 400;
  }
  .recommend-more {
    font-size: 12px;
    font-weight: 400;
    color: #999;
  }
  .row .recommend-item {
    padding: 10px 0 10px 0;
    border-top: 1px solid #eee;
  }
  .recommend-item-title {
    font-size: 14px;
    font-weight: 700;
    color: #259;
  }
  .recommend-item-meta {
    color: #999;
    font-weight: 400;
  }
</style>
