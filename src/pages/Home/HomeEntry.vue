<template lang="html">
  <div class="home-entry">
    <b-media>
      <img class="avator" slot="aside" src="https://pic2.zhimg.com/c320496bb2fb33943a2c30ff4439b7bd_s.jpg" alt="">
      <b-nav class="home-entry-list">
        <b-nav-item>
          <a href="#">
            <i class="fa fa-question-circle-o"></i>
            提问
          </a>
        </b-nav-item>
        <b-nav-item>|</b-nav-item>
        <b-nav-item>
          <a href="#">
            <i class="fa fa-list"></i>
            回答
          </a>
        </b-nav-item>
        <b-nav-item>|</b-nav-item>
        <b-nav-item>
          <a href="#">
            <i class="fa fa-pencil-square-o "></i>
            写文章
          </a>
        </b-nav-item>
        <b-nav-item class="ml-auto">
          <a href="#">
            草稿
          </a>
        </b-nav-item>
      </b-nav>
  </b-media>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="css">
  .avator {
    width: 38px;
    height: 38px;
    border-radius: .25rem;
  }

  .home-entry-list {
    background: #fafafa;
    border: 1px solid #f0f0f0;
    border-radius: 4px;
  }
</style>
