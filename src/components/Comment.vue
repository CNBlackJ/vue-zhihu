<template lang="html">
  <div id="comment">
    <div class="comment-panel">
      <div class="comment-header">
        <span class="header-left">
            {{commentCount}}条评论
        </span>
        <span class="pull-right">
            切换为时间进行排序
        </span>
      </div>

      <div class="comment-entity" v-for="(reply, index) in replies">
        <div :id="index" v-on:mouseover="isShow(index)" v-on:mouseout="isShow(index)" class="comment-user">
          <img class="avatar" slot="aside" :src="reply.author.avatar_url" alt="">
          <a href="#" class="comment-username">
              {{ reply.author.loginname }}
          </a>
          <span class="bg-grey pull-right">12小时前</span>
          <div class="comment-detail">
            <p class="comment-content" v-html="reply.content"></p>
            <a href="#" class="bg-grey">
                <i class="fa fa-thumbs-up fa-1"></i>
                {{ reply.ups.length }}
            </a>
            <a href="#" class="bg-grey" v-show="index === hoverId">
              <i class="fa fa-reply fa-1"></i>
              回复
            </a>
            <a href="#" class="bg-grey" v-show="index === hoverId">
              <i class="fa fa-thumbs-down fa-1"></i>
              踩
            </a>
            <a href="#" class="bg-grey" v-show="index === hoverId">
              <i class="fa fa-exclamation-circle fa-1"></i>
              举报
            </a>
          </div>
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
      skip: 0,
      limit: 10,
      replies: [],
      hoverId: -1
    }
  },
  props: ['commentCount', 'postId'],
  created: async function () {
    this.replies = await this.fetchReplies()
  },
  methods: {
    fetchReplies: async function () {
      const response = await axios.get(`https://cnodejs.org/api/v1/topic/${this.postId}`)
      const replies = response.data.data.replies
      return replies.slice(this.skip, this.skip + this.limit)
    },
    isShow: function (id) {
      this.hoverId = this.hoverId === -1 ? id : -1
    }
  }
}
</script>

<style lang="css">
  .comment-header {
    border-bottom: 1px solid #f0f2f7;
    height: 50px;
    padding: 15px 20px 0 20px;
  }
  .header-left {
    font-size: 15px;
    font-weight: 700;
  }
  .header-right {
    font-size: 14px;
  }
  .comment-user {
    padding-left: 8px;
    padding-right: 8px;
  }
  .comment-entity {
    margin: 0px;
    padding: 12px 16px 10px 16px;
  }
  .comment-panel {
    /* width: 70%; */
    border: 1px solid #ddd;
    border-radius: 4px;
    box-shadow: 0 1px 1px rgba(0,0,0,.05);
    /* padding: 16px; */
  }
  .comment-username {
    font-size: 14px;
    padding-left: 5px;
  }
  .comment-detail {
    padding-left: 0px;
  }
  .comment-detail a {
    padding-right: 15px;
    font-size: 14px;
  }
  .comment-content {
    margin: 0px;
    padding-top: 5px;
    padding-bottom: 5px;
    font-size: 14px;
  }
  .comment-content p {
    margin-bottom: 0px;
  }
  .bg-grey {
    color: #999;
  }
</style>
