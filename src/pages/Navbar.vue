<template lang="html">
  <div class="navbar">
    <b-navbar toggleable type="inverse" variant="primary">

        <b-nav-toggle target="nav_collapse"></b-nav-toggle>

        <b-link class="navbar-brand" to="#">
          <span>ZHIHU</span>
        </b-link>

        <b-collapse is-nav id="nav_collapse">

          <b-nav>
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

              <!-- Using text slot -->
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
.badge {
  background-color: red;
  border-radius: 0.75rem;
}
</style>
