<template>
  <form
    class="main-form"
    @submit.prevent
    autocomplete="off"
    :class="{ 'form-group--error': $v.email.$error }"
  >
    <input
      type="text"
      id="full_name"
      class="main-form__full-names"
      placeholder="Full names"
      v-model:trim="$v.first_name.$model"
    />

    <input
      type="text"
      id="email"
      class="email"
      placeholder="Email Address"
      v-model:trim="$v.email.$model"
    />

    <div class="error" v-if="!validEmail && $v.email.required">
      Email Field is required and should be valid
    </div>

    <input
      type="password"
      id="password"
      class="password"
      placeholder="Password"
      v-model="password"
    />
    <div class="error" v-if="!$v.password.required">
      Password field must be at least 6 characters long
    </div>
    <input
      type="password"
      id="confirm_password"
      class="password"
      placeholder="Confirm Password"
      v-model="password"
    />
    <a href="" class="forgot_password"> forgot password ?</a>

    <input type="submit" class="login_btn" value="Log In" />
    <div class="main-form__terms">
      <input type="checkbox" id="checkbox" />
      <label for="checkbox" class="main-form__terms--condition">
        I have read and agree to the
        <a href="#">Terms of service</a>
      </label>
    </div>
  </form>
</template>

<script>
import { required, minLength, between } from "vuelidate/lib/validators";
export default {
  data() {
    return {
      first_name: "",
      last_name: "",
      email: "",
      password: ""
    };
  },
  validations: {
    first_name: {
      required,
      minLength: minLength(6)
    },
    last_name: {
      required,
      minLength: minLength(6)
    },

    email: {
      required,
      minLength: minLength(6)
    },
    password: {
      required,
      minLength: minLength(6)
    }
  },
  computed: {
    validEmail() {
      return /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(this.email);
    }
  }
};
</script>

<style lang="scss" scoped>
.login-container {
  display: flex;
  flex-direction: column;

  padding: 3rem;
  margin-top: 4rem;
}
.error {
  color: var(--secondary-color);
  font-size: 16px;
}

.email {
  height: 40px;
  margin: 0;

  width: 100%;
  background-color: transparent;

  outline: none;
  border: none;
  color: var(--input-color);

  border-bottom: 1px solid var(--input-color);
}
.password {
  height: 40px;
  margin-top: 1rem;

  width: 100%;
  background-color: transparent;
  color: var(--input-color);
  outline: none;
  border: none;
  border-bottom: 1px solid var(--input-color);
}

.forgot_password {
  margin-top: 1rem;
  font-size: 12px;
  align-self: flex-end;
}

.login_btn {
  text-align: center;

  width: 70%;
  height: 40px;
  margin-top: 10px;
  align-self: center;
  border: none;

  text-decoration: none;
  background-color: var(--secondary-color);
  color: white;
  outline: none;
  transition: transform 0.5s;

  &:hover {
    transform: translateY(-10px);
  }
}
.main-form {
  margin-top: 2rem;
  display: flex;
  flex-direction: column;
  position: relative;

  &__email-input {
    position: relative;
  }

  &__full-names {
    height: 40px;

    margin-top: 1rem;
    margin-bottom: 1rem;
    width: 100%;
    background-color: transparent;

    outline: none;
    border: none;
    color: var(--input-color);

    border-bottom: 1px solid var(--input-color);
  }

  &__terms {
    margin-top: 2rem;

    &--condition {
      font-size: 1.2rem;
    }
  }
  &__forgot_password {
    text-decoration: none;
    margin-top: 1rem;
    font-size: 1.3rem;
    display: flex;
    justify-content: flex-end;
  }
}
</style>
