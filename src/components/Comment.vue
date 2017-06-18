<template lang="html">
  <div id="comment">
    <div class="comment-panel">
      <div class="row" v-for="reply in replies">
        <div class="comment-avatar">
          <img class="avatar" slot="aside" :src="reply.author.avatar_url" alt="">
        </div>
        <div class="comment-detail">
          <a href="#">
            {{ reply.author.loginname }}
          </a>
          <p class="comment-content" v-html="reply.content"></p>
          <span class="bg-grey">12小时前</span>
          <a href="#" class="bg-grey">
            <i class="fa fa-reply fa-1"></i>
            回复
          </a>
          <a href="#" class="bg-grey">
            <i class="fa fa-thumbs-up fa-1"></i>
            赞
          </a>
          <a href="#" class="bg-grey">
            <i class="fa fa-thumbs-down fa-1"></i>
            踩
          </a>
          <a href="#" class="bg-grey">
            <i class="fa fa-exclamation-circle fa-1"></i>
            举报
          </a>
          <span class="bg-grey">
            {{ reply.ups.length }}赞
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      replies: []
    }
  },
  created: async function () {
    this.replies = await this.fetchReplies()
  },
  methods: {
    fetchReplies: async function () {
      const response = await axios.get('https://cnodejs.org/api/v1/topic/5433d5e4e737cbe96dcef312')
      const replies = response.data.data.replies
      return replies
    }
  }
}
</script>

<style lang="css">
  .comment-avatar {
    padding-left: 8px;
    padding-right: 8px;
  }
  .comment-panel {
    width: 70%;
    border: 1px solid #ddd;
    border-radius: 4px;
    box-shadow: 0 1px 1px rgba(0,0,0,.05);
    padding: 16px;
  }
  .comment-detail {
    padding-left: 0px;
  }
  .comment-content {
    margin: 0px;
    padding-top: 5px;
    padding-bottom: 5px;
  }
  .bg-grey {
    color: #999;
  }
</style>
