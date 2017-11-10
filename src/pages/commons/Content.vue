<template lang="html">
  <div class="content">
    <div class="content-header" v-if="isHome">
      <span class="fa fa-list-alt pull-left">
        最新动态
      </span>
      <span class="fa fa-cog pull-right">
        设置
      </span>
    </div>

    <div v-for="(topic, index) in topics" class="content-section">
      <b-media :id="index">
        <div class="row">
          <div class="col-md-1" style="padding: 0px">
            <div class="topic-avatar" v-if="isHome">
              <img class="avatar" slot="aside" :src="topic.author.avatar_url" alt="">
            </div>

            <vote :isShowAll="showId === index && isShowAll"></vote>
          </div>

          <div class="topic-header row col-md-11" style="padding: 0px">
            <div class="col-md-12" style="padding: 0px">
              <div class="topic-from" v-if="isHome">
                来自话题: {{ topic.tab }}
                <i class="pull-right fa fa-remove"></i>
              </div>
              <div class="topic-title">
                <a href="#">{{ topic.title }}</a>
              </div>
              <div class="user-name">
                作者：<a href="">{{ topic.author.loginname }}</a>
              </div>
              <div class="topic-content">
                <div v-on:mouseover="isActive=true" v-on:mouseout="mouseOver(index)" class="topic-description">

                  <div v-show="showId === index && isShowAll" class="markdown-content" v-html="topic.content"></div>
                  <div v-show="!(showId === index && isShowAll)" class="markdown-content" v-html="getRawContent(topic.content)"></div>

                  <a v-if="!(showId === index && isShowAll)" v-on:click="showAll(index)" v-bind:class="{ 'show-all-hover': isActive && index === hoverId }">显示全部</a>

                  <div class="topic-meta">
                    <div>
                      <a href="#">
                        <i class="fa fa-plus fa-1"></i>
                        关注问题
                      </a>
                      <a href="#" v-on:click="showComment(index)">
                        <i class="fa fa-comment-o fa-1"></i>
                        {{ topic.reply_count }}条评论
                      </a>
                      <a v-show="!(isActive && index === hoverId)" href="#">
                        <i class="">•</i>
                        禁止转载
                      </a>
                      <a href="#" v-show="isActive && index === hoverId">
                        <i class="fa fa-heart-o fa-1"></i>
                        感谢
                      </a>
                      <a href="#" v-show="isActive && index === hoverId">
                        <i class="fa fa-share-square fa-1"></i>
                        分享
                      </a>
                      <a href="#" v-show="isActive && index === hoverId">
                        <i class="fa fa-bookmark-o fa-1"></i>
                        收藏
                      </a>
                      <a href="#" v-show="isActive && index === hoverId">
                        <i class="">•</i>
                        没有帮助
                      </a>
                      <a href="#" v-show="isActive && index === hoverId">
                        <i class="">•</i>
                        举报
                      </a>
                      <a href="#" v-show="isActive && index === hoverId">
                        <i class="">•</i>
                        作者保留权利
                      </a>
                    </div>
                    <div class="pull-left">
                      <a v-show="showId === index && isShowAll" class="pull-right" v-on:click="showLess">
                        <i class="fa fa-caret-up"></i>
                        收起
                      </a>
                    </div>
                  </div>
                </div>
              </div>
              <div class="">
                <comment :commentCount="topic.reply_count" :postId="topic.id" v-if="index === showCommentId">
                </comment>
              </div>
            </div>
          </div>
        </div>
      </b-media>
    </div>
  </div>
</template>

<script>
import vote from './Vote'
import axios from 'axios'
import comment from '../../components/Comment'

export default {
  data () {
    return {
      isActive: false,
      isShowAll: false,
      vote: 0,
      content: '',
      topics: [],
      showId: -1,
      hoverId: -1,
      showCommentId: -1
    }
  },
  props: ['isHome'],
  components: {
    vote,
    comment
  },
  created: async function () {
    this.topics = await this.fetchTopics()
  },
  methods: {
    fetchTopics: async function () {
      const response = await axios.get('https://cnodejs.org/api/v1/topics?limit=10')
      const topics = response.data.data
      return topics
    },
    getRawContent: function (content) {
      return content.replace(/<[^>]+>/g, '').substr(0, 200) + '...'
    },
    mouseOver: function (id) {
      if (this.isShowAll) {
        this.isActive = true
      } else {
        this.hoverId = id
        this.isActive = false
      }
    },
    showAll: async function (id) {
      this.showId = id
      this.isShowAll = true
    },
    showLess: function () {
      this.isShowAll = false
    },
    showComment: function (index) {
      this.showCommentId = this.showCommentId === -1 ? index : -1
    }
  }
}
</script>

<style lang="css">
  .fa.fa-1 {
    font-size: .1em;
  }
  .topic-meta {
    padding-top: 7px;
  }
  .topic-meta a {
    padding-right: 7px;
    color: #999;
  }
  /* .topic-content {
    width: 70%;
  } */
  .topic-description {
    padding-top: 7px;
  }
  .show-all-hover {
    background: #eff6fa;
    text-decoration: none;
  }
  .topic-vote {
    background: #eff6fa;
    color: #698ebf;
    border: 0px;
    font-weight: 500;
    text-align: center;
    width: 38px;
    height: 24px;
    padding-top: 2px;
    margin-top: 5px;
    border-radius: 3px;
  }
  .topic-from {
    color: #999;
  }
  .avatar {
    width: 38px;
    height: 38px;
    border-radius: 3px;
  }
  .user-name {
    font-size: 13px;
    padding-top: 7px;
  }
  .content-header {
    overflow: hidden;
    padding: 30px 0 10px 0;
    border-bottom: 1px solid #ccc;
  }
  .content-header .pull-left {
    font-size: 14px;
    font-weight: 700;
    color: #666;
  }
  .content-header .pull-right {
    font-weight: 400;
    color: #999;
  }
  .content-section {
    padding-top: 10px;
  }
  .topic-title {
    font-size: 14px;
    padding-top: 7px;
  }
  .markdown-content img {
    width: 100%;
  }
  .markdown-text a {
    color: #259;
  }
  .markdown-text ul {
    display: block;
  }
  .markdown-text li {
    display: list-item;
  }
</style>
