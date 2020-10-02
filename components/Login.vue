<template>
  <form class="login-container" @submit.prevent>
    <div class="title">Login</div>

    <div class="input-icon" :class="{ 'form-group--error': $v.email.$error }">
      <div class="input-icon__icon-container">
        <icon-base
          width="20"
          height="25"
          icon-name="user"
          icon-color="grey"
          class="input-icon__icon"
        >
          <IconEmail
        /></icon-base>
      </div>
      <input
        type="text"
        id="email"
        class="input-icon__email"
        placeholder="Email"
        v-model:trim="$v.email.$model"
      />
    </div>
    <div class="error" v-if="!$v.email.required">Email Field is required</div>
    <div class="error" v-if="!$v.email.minLength">
      Email must have at least {{ $v.email.$params.minLength.min }} letters.
    </div>
    <!--
    <div v-if="!validEmail && email !== ''" class="danger">
      Invalid Email Address
    </div>
    -->
    <div class="input-icon">
      <div class="input-icon__icon-container">
        <icon-base
          width="20"
          height="20"
          icon-name="icon"
          icon-color="grey"
          class="input-icon__icon"
        >
          <IconLock
        /></icon-base>
      </div>
      <input
        type="password"
        id="email"
        class="input-icon__password"
        placeholder="password"
        v-model="password"
      />
    </div>
    <a href="" class="forgot_password"> forgot password ?</a>

    <input type="submit" class="login_btn" />
  </form>
</template>

<script>
import { required, minLength, between } from "vuelidate/lib/validators";
export default {
  data() {
    return {
      email: "",
      password: ""
    };
  },
  validations: {
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
  background-color: white;
  display: flex;
  flex-direction: column;

  padding: 3rem;
  margin-top: 7rem;
  border-radius: 1rem;
  width: 35%;
  min-height: 50vh;
  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
}
.danger {
  color: red;
  font-size: 10px;
  margin-left: 40px;
}
.input-icon {
  position: relative;
  padding: 0 0 0 22px;

  &__icon-container {
    position: absolute;
    bottom: 4px;
    left: 25px;
    padding-left: 5px;

    border-radius: 2px;
  }

  &__email {
    height: 40px;
    margin: 0;
    padding-left: 30px;
    width: 100%;
    border: 1px solid #eee;

    outline: none;
  }
  &__password {
    height: 40px;
    margin-top: 1rem;
    padding-left: 30px;
    width: 100%;
    border: 1px solid #eee;

    outline: none;
  }
}

.title {
  font-size: 2rem;
  font-weight: bold;
  font-family: "Montserrat", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
  text-align: center;
}
.forgot_password {
  text-decoration: none;
  margin-top: 1rem;
  font-size: 12px;
  display: flex;
  justify-content: flex-end;
}
.have-account {
  margin-top: 1rem;
  display: flex;
  justify-content: center;
  font-size: 1.7rem;
}

.login_btn {
  text-align: center;

  width: 70%;
  height: 40px;
  margin-top: 10px;
  align-self: center;
  border: none;
  border-radius: 10px;

  text-decoration: none;
  background-color: var(--color-primary-pink);
  color: white;
  outline: none;
  transition: transform 0.5s, opacity 0.5s;

  &:hover {
    background-color: var(--color-primary-pink);
    opacity: 0.8;
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

  &__first-name {
    height: 4rem;
    outline: none;
    border: 1px solid #eee;
    border-radius: 1rem;
    padding: 0 1rem;
    font-family: "Montserrat";
    transition: transform 0.3s;
    &:focus {
      transform: translateY(-1.5rem) scale(1.03);
    }
  }

  &__last-name {
    height: 4rem;
    margin-top: 1rem;
    outline: none;
    border: 1px solid #eee;
    border-radius: 1rem;
    padding: 0 1rem;
    font-family: "Montserrat";
    transition: transform 0.3s;
    &:focus {
      transform: translateY(-1.5rem) scale(1.03);
    }
  }
  &__email {
    height: 4rem;
    margin-top: 1rem;
    outline: none;
    border: 1px solid #eee;
    border-radius: 1rem;
    padding: 0 1rem;
    font-family: "Montserrat";
    &:focus {
      transform: translateY(-1.5rem) scale(1.03);
    }
  }
  &__password {
    height: 4rem;
    margin-top: 1rem;
    outline: none;
    border: 1px solid #eee;
    border-radius: 1rem;
    padding: 0 1rem;
    font-family: "Montserrat";
    transition: transform 0.3s;
    &:focus {
      transform: translateY(-1.5rem) scale(1.03);
    }
  }
  &__sign-up {
    height: 4rem;
    margin-top: 1.5rem;
    font-size: 1.5rem;
    border: none;
    background-color: var(--color-blue);
    color: white;
    font-family: "Montserrat";
    border-radius: 1rem;
  }

  &__terms {
    margin-top: 2rem;

    &--condition {
      font-size: 1.4rem;
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
