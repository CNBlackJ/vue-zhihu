<template>
  <div class="login">
    <div class="row">
      <div class="col-md-3"></div>
      <div class="col-md-6">
        <div class="row form-group">
          <label for="email" class="control-label col-md-4">Email</label>
          <div class="col-md-8" :class="{ 'control': true }">
            <b-form-input
              name="email"
              type="text"
              placeholder="Enter your email"
              v-validate="'required|email'"
              :class="{'input': true, 'is-danger': errors.has('email') }"
              v-model="email">
            </b-form-input>
            <span v-show="errors.has('email')" class="help is-danger">{{ errors.first('email') }}</span>
          </div>
        </div>

        <div class="row form-group">
          <label for="password" class="control-label col-md-4">Password</label>
          <div class="col-md-8">
            <b-form-input
              name="password"
              type="password"
              placeholder="Enter your password"
              class="form-control"
              v-validate="'required|min:6|max:16'"
              :class="{'input': true, 'is-danger': errors.has('password') }"
              v-model="password">
            </b-form-input>
            <span
              v-show="errors.has('password')"
              class="help is-danger">{{ errors.first('password') }}
            </span>
          </div>
        </div>

        <div class="form-group row">
          <div class="col-md-4"></div>
          <div class="col-md-6">
            <b-button v-on:click="signIn">Sign In</b-button>
          </div>
        </div>
      </div>
      <div class="col-md-3"></div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'login',
    data () {
      return {
        email: null,
        password: '',
        isLogin: false
      }
    },
    methods: {
      signIn: function () {
        const email = this.email
        const password = this.password
        if (email === 'a@qq.com' && password === '123456') window.location = '/'
      }
    }
  }
</script>
