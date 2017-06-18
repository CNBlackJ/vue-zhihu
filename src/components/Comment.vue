<template lang="html">
  <div id="comment">
    <div class="comment-panel">
      <div class="row">
        <div class="comment-avatar">
          <img class="avatar" slot="aside" src="https://avatars0.githubusercontent.com/u/3118295?v=3&s=120" alt="">
        </div>
        <div class="comment-detail">
          <a href="#">
            关小民
          </a>
          <p class="comment-content">这是多大仇</p>
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
            792赞
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      replies: [{id: '1'}, {id: '2'}]
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
