<template lang="html">
  <div class="content">
    <div class="content-header">
      <span class="fa fa-list-alt pull-left">
        最新动态
      </span>
      <span class="fa fa-cog pull-right">
        设置
      </span>
    </div>

    <br>

    <div class="content-section">
      <b-media>
        <div class="row">
          <div class="col-md-1">
            <div class="topic-avatar">
              <img class="avatar" slot="aside" src="https://pic2.zhimg.com/c320496bb2fb33943a2c30ff4439b7bd_s.jpg" alt="">
            </div>
            <a v-on:click="addVote">
              <div class="topic-vote">
                {{ vote }}
              </div>
            </a>
          </div>

          <div class="topic-header row col-md-11">
            <div class="col-md-12">
              <div class="topic-from">
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
                <div class="topic-description">
                  {{ content }}
                  <a class="show-all" href="#">显示全部</a>
                </div>

                <div class="topic-meta">
                  <a href="#">
                    <i class="fa fa-plus fa-1"></i>
                    关注问题
                  </a>
                  <a href="#">
                    <i class="fa fa-comment-o fa-1"></i>
                    335条评论
                  </a>
                  <a href="#">
                    <i class="fa fa-circle fa-1"></i>
                    禁止转载
                  </a>
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
export default {
  data () {
    return {
      vote: 0,
      content: '太多人把微信当作一个神一样的产品了。 也有太多人把张小龙当作神了。 知乎不是一个崇尚独立思考的地方吗？ 它真的是那么好吗，还是说就是为了自我安慰“我用的应该是个好产品”而心里作祟在说“好”。 就我而言，我认为微信并没有什么突出的地方，并不是一…'
    }
  },
  methods: {
    addVote: function () {
      this.vote += 1
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
  .topic-description:hover {
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
    padding-top: 30px;
  }

  .content-section {
    border-top: 1px solid #ccc;
    padding-top: 10px;
  }

  .topic-title {
    font-size: 14px;
    padding-top: 7px;
  }
</style>
