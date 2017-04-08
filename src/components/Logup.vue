<template>
  <div class="logup">
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
              v-validate="'required|min:6|max:16|confirmed:confirmpassword'"
              :class="{'input': true, 'is-danger': errors.has('password') }"
              v-model="password">
            </b-form-input>
          </div>
        </div>

        <div class="row form-group">
          <label for="confirmpassword" class="control-label col-md-4">Confirm</label>
          <div class="col-md-8">
            <b-form-input
              name="confirmpassword"
              type="password"
              class="form-control"
              placeholder="Confirm Your Password.">
            </b-form-input>
            <span v-show="errors.has('password')" class="help is-danger">{{ errors.first('password') }}</span>
          </div>
        </div>

        <div class="form-group row">
          <div class="col-md-4"></div>
          <div class="col-md-6">
            <b-button v-on:click="addUser">Sign Up</b-button>
          </div>
        </div>
      </div>
      <div class="col-md-3"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'logup',
  data () {
    return {
      email: null,
      password: '',
      users: []
    }
  },
  methods: {
    addUser: function () {
      const user = {
        email: this.email,
        password: this.password
      }
      this.users.push(user)
    }
  }
}
</script>
