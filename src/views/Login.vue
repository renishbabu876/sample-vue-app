

<template>
  <div class="inner-form-bg w-100 vh-100 position-relative">
    <b-container class="position-absolute main-form">
      <b-row class="w-75 m-auto bg-white border shadow form-content">
        <b-col sm="6" class="main-bg">
          <img
            src="../assets/img/restarault-form-img.svg"
            class="w-100 h-100"
          />
        </b-col>
        <b-col sm="6" class="py-5 inner-bg--1">
          <div class="inner-bg-grey">
            <div>
              <b-form >
                <b-form-group
                  id="input-group-1"
                  label="Email address"
                  label-for="input-1"
                >
                  <b-form-input
                    id="input-1"
                    v-model="form.email"
                    type="email"
                    placeholder="Enter email"
                    required
                  ></b-form-input>
                </b-form-group>

                <b-form-group
                  id="input-group-2"
                  label="Password"
                  label-for="input-2"
                >
                  <b-form-input
                    type="password"
                    id="input-2"
                    placeholder="Enter password"
                    required
                    v-model="form.password"
                    v-on:input="password"
                  ></b-form-input>
                </b-form-group>
                <small id="passwordHelp" class="form-text text-muted"
                  >Password should contain
                  <span :class="has_minimum_lenth ? 'has_required' : '' "
                    >atleast 10 chacters</span
                  >
                </small>

                <b-button
                  @click="submit"
                  type="submit"
                  variant="outline-primary"
                  class="px-5 py-2 rounded-pill"
                  >Login</b-button
                >
              </b-form>
            </div>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: "",
        password: "",
      },

      has_minimum_lenth: false,
    };
  },

  methods: {
    submit() {
      console.log(this.form);
    },
      password() {
      this.has_minimum_lenth = this.form.password.length > 8;
    }
  },
};
</script>

<style lang="scss" scoped>
.inner-form-bg {
  .main-form {
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }

  .main-bg {
    background: #e0f0f3;
  }
  .inner-bg--1 {
    background: white;
  }
}
</style>


