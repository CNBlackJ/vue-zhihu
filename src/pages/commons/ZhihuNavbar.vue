<template lang="html">
  <div class="zhihunavbar">
    <b-navbar toggleable type="inverse" variant="primary">
        <div class="col-md-2"></div>
        <div class="col-md-8 navbar-content">
          <b-collapse is-nav id="nav_collapse" class="nav-collapse">
            <b-nav>
              <b-link class="navbar-brand" to="#">
                <span>ZhiHu</span>
              </b-link>
              <b-form-input
                type="text"
                placeholder="Search interesting ..."
                >
              </b-form-input>
            </b-nav>

            <b-nav is-nav-bar>
              <b-nav-item :active='true'>Home</b-nav-item>
              <b-nav-item>Topic</b-nav-item>
              <b-nav-item>Discover</b-nav-item>
              <b-nav-item>
                Message
                <span class="badge">4</span>
              </b-nav-item>
            </b-nav>

            <b-nav is-nav-bar class="ml-auto">

              <b-nav-item>
                Question
              </b-nav-item>

              <b-nav-item-dropdown v-if=isLogin right-alignment>

                <template slot="text">
                  <img slot="aside" src="https://pic2.zhimg.com/c320496bb2fb33943a2c30ff4439b7bd_s.jpg" alt="">
                  <span style="font-weight: bold;">User</span>
                </template>

                <b-dropdown-item to="#">Profile</b-dropdown-item>
                <b-dropdown-item to="#">Signout</b-dropdown-item>
              </b-nav-item-dropdown>

              <b-nav v-else>
                <b-nav-item>
                  SignIn
                </b-nav-item>

                <b-nav-item>
                  SignUp
                </b-nav-item>
              </b-nav>

            </b-nav>
          </b-collapse>
        </div>
        <div class="col-md-2"></div>

    </b-navbar>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isLogin: true
    }
  }
}
</script>

<style lang="css">
.zhihunavbar {
  padding: 0;
}
.col-md-8.navbar-content {
  padding: 0;
}
.nav-collapse {
  height: 32px;
}
.badge {
  background-color: red;
  border-radius: 0.75rem;
}
</style>
