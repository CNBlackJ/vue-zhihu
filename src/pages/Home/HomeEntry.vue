<template lang="html">
  <div class="home-entry row">
    <div class="col-md-1">
      <img class="avator" slot="aside" src="https://pic2.zhimg.com/c320496bb2fb33943a2c30ff4439b7bd_s.jpg" alt="">
    </div>
    <div class="home-entry-box">
      <ul>
        <li class="home-entry-item">
          <a href="#">
            <i class="fa fa-question-circle-o"></i>
            提问
          </a>
        </li>
        <li class="home-entry-item">
          <a href="#">
            <i class="fa fa-list"></i>
            回答
          </a>
        </li>
        <li class="home-entry-item">
          <a href="#">
            <i class="fa fa-pencil-square-o "></i>
            写文章
          </a>
        </li>
        <li class="pull-right home-entry-draft">
          <a href="#">
            草稿
          </a>
        </li>
      </ul>
    </div>
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
  .home-entry-box {
    height: 48px;
    line-height: 48px;
    background: #fafafa;
    border: 1px solid #f0f0f0;
    border-radius: 4px;
    position: relative;
  }
  .home-entry-draft {
    padding: 0 20px 0 100px;
  }
  .home-entry-draft a {
    color: #999;
  }
  .home-entry-box ul {
    padding: 0;
    margin: 0;
  }
  .home-entry-list {
    background: #fafafa;
    border: 1px solid #f0f0f0;
    border-radius: 4px;
  }
  .home-entry-item {
    padding: 0 32px 0 27px;
    font-size: 14px;
  }
  .home-entry-item a {
    color: #6c829f;
  }
  .home-entry-item a:hover {
    color: #259;
    text-decoration: none;
  }
</style>
