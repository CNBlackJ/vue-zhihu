<template lang="html">
  <div class="content">
    <div class="content-header" v-show="isHome">
      <span class="fa fa-list-alt pull-left">
        最新动态
      </span>
      <span class="fa fa-cog pull-right">
        设置
      </span>
    </div>

    <div class="content-section">
      <b-media>
        <div class="row">
          <div class="col-md-1" style="padding: 0px">
            <div class="topic-avatar" v-show="isHome">
              <img class="avatar" slot="aside" src="https://pic2.zhimg.com/c320496bb2fb33943a2c30ff4439b7bd_s.jpg" alt="">
            </div>

            <vote :isShowAll=isShowAll></vote>
          </div>

          <div class="topic-header row col-md-11" style="padding: 0px">
            <div class="col-md-12" style="padding: 0px">
              <div class="topic-from" v-show="isHome">
                来自话题: IT 行业
                <i class="pull-right fa fa-remove"></i>
              </div>
              <div class="topic-title">
                <a href="#">为什么想着更多的人用微信而不是QQ</a>
              </div>
              <div class="user-name">
                匿名用户
              </div>
              <div class="topic-content">
                <div v-on:mouseover="active=true" v-on:mouseout="mouseOver" class="topic-description">
                  {{ content }}
                  <a v-if="!isShowAll" v-on:click="showAll" v-bind:class="{ 'show-all-hover': active }">显示全部</a>

                  <div class="topic-meta">
                    <a href="#">
                      <i class="fa fa-plus fa-1"></i>
                      关注问题
                    </a>
                    <a href="#">
                      <i class="fa fa-comment-o fa-1"></i>
                      335条评论
                    </a>
                    <a v-show="!active" href="#">
                      <i class="">•</i>
                      禁止转载
                    </a>
                    <a v-show="active" href="#">
                      <i class="fa fa-heart-o fa-1"></i>
                      感谢
                    </a>
                    <a v-show="active" href="#">
                      <i class="fa fa-share-square fa-1"></i>
                      分享
                    </a>
                    <a v-show="active" href="#">
                      <i class="fa fa-bookmark-o fa-1"></i>
                      收藏
                    </a>
                    <a v-show="active" href="#">
                      <i class="">•</i>
                      没有帮助
                    </a>
                    <a v-show="active" href="#">
                      <i class="">•</i>
                      举报
                    </a>
                    <a v-show="active" href="#">
                      <i class="">•</i>
                      作者保留权利
                    </a>
                    <a v-show="isShowAll" class="pull-right" v-on:click="showDesc">
                      <i class="fa fa-caret-up"></i>
                      收起
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- [Optional: add media children here for nesting] -->
      </b-media>
    </div>
  </div>
</template>

<script>
import vote from './Vote'

export default {
  data () {
    return {
      active: false,
      isShowAll: false,
      vote: 0,
      content: '太多人把微信当作一个神一样的产品了。 也有太多人把张小龙当作神了。 知乎不是一个崇尚独立思考的地方吗？ 它真的是那么好吗，还是说就是为了自我安慰“我用的应该是个好产品”而心里作祟在说“好”。 就我而言，我认为微信并没有什么突出的地方，并不是一…'
    }
  },
  props: ['isHome'],
  components: {
    vote
  },
  methods: {
    mouseOver: function () {
      if (this.isShowAll) {
        this.active = true
      } else {
        this.active = false
      }
    },
    showAll: function () {
      this.content = '我生活在一个性教育普及很早的环境，不是从课本上，而是从……小黄片上（捂脸），我初中的时候，我们班青春期的躁动的小男生啊，可能作妖了啊，各种渠道找了n多小黄片，星状散步出去.本来也挺好的，青春期的孩子对性本来就应该有所了解的是不是？可是你们为什么要发给我？？？你们还记不记得我是个女的啊？？我还是个好奇心那么重的女的啊？？？我怎么可能不看呢！！！我还记得那天风和日丽，我爸出去斗地主，我妈出去打麻将，家里只剩我！只剩我！！！（仰天大笑）迅速打开电脑，播放.讲真，其实不怎么好看，但是好奇心驱使我一定要看到关键时刻！然后！我房门被打开了！！！我老娘回来了！！！'
      this.isShowAll = true
    },
    showDesc: function () {
      this.content = '太多人把微信当作一个神一样的产品了。 也有太多人把张小龙当作神了。 知乎不是一个崇尚独立思考的地方吗？ 它真的是那么好吗，还是说就是为了自我安慰“我用的应该是个好产品”而心里作祟在说“好”。 就我而言，我认为微信并没有什么突出的地方，并不是一…'
      this.isShowAll = false
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
</style>
