<template>
  <div class="modal-backdrop">
    <div class="top-side">
      <div class="lhs">
        <div class="logo">
          <img src="~assets/img/StartX-logo-white.png" alt="">
        </div>
      </div>
      <div class="rhs">
        <div v-if="accountCreated === false" class="modal">
          <h1 class="title">
            Create An Account!
          </h1>
          <p class="sub-title">
            Register with your account details to begin.
          </p>
          <div class="form">
            <div class="input-div">
              <div class="input-box">
                <p class="label">
                  First Name
                </p>
                <input v-model="first_name" type="text" name="" placeholder="Enter First Name">
              </div>
              <div class="input-box">
                <p class="label">
                  Last Name
                </p>
                <input v-model="last_name" type="text" name="" placeholder="Enter Last Name">
              </div>
            </div>
            <div class="input-container">
              <p class="label">
                Email Address
              </p>
              <input v-model="email" type="email" name="" placeholder="Enter Email Address">
            </div>
            <div class="input-container">
              <p class="label">
                Mobile Number
              </p>
              <input v-model="phone_number" type="number" name="" placeholder="Enter Mobile Number">
            </div>
            <div class="input-container">
              <p class="label">
                Password
              </p>
              <div class="password-input">
                <input v-model="password" class="pass-input" :type="type" placeholder="Enter Password">
                <p class="show-hide" @click="showHide()">
                  {{ show_hide }}
                </p>
              </div>
            </div>
            <div class="btn">
              <button v-if="loading">
                <Loader />
              </button>
              <button v-else @click="register()">
                Register
              </button>
            </div>
            <p class="text">
              Already have an account?
            </p>
            <NuxtLink to="/login">
              <p class="create-acct">
                Login
              </p>
            </NuxtLink>
          </div>
        </div>
      </div>
    </div>
    <!-- <p class="link">
      www.startx.ng
    </p> -->
    <AccountCreated v-if="accountCreated" />
  </div>
</template>

<script>
import Cookies from 'js-cookie'
import Loader from '~/components/Loader.vue'
import AccountCreated from '~/components/Modals/AccountCreated.vue'
export default {
  components: {
    AccountCreated,
    Loader
  },
  data () {
    return {
      accountCreated: false,
      loading: false,
      first_name: '',
      last_name: '',
      email: '',
      phone_number: '',
      password: '',
      pin: '',
      comfirm_password: '',
      type: 'password',
      show_hide: 'show',
      C_type: 'password',
      pin_type: 'password',
      C_show_hide: 'show',
      pin_show_hide: 'show',
      publicToken: ''
    }
  },
  computed: {
    validEmail () {
      // eslint-disable-next-line no-useless-escape
      const re = /^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
      return re.test(this.email)
    },
    allFieldsValid () {
      return this.firstname && this.lastname &&
      this.phoneNumber && this.phoneNumberValid && this.validEmail && this.passwordEligible && !this.error
    }
  },
  watch: {
    allFieldsValid (val) {
      if (val === true) {
        this.generalError = false
      } else {
        this.generalError = true
      }
    },
    email () {
      this.error = ''
    },
    phoneNumber (val) {
      if (val?.length >= 11) {
        this.phoneNumber = val.substring(0, val.length - 1)
      }
    }
  },
  created () {
    this.publicToken = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI2MjdhOGUxZDliMjVkMThiZjVhNDRmZWQiLCJpYXQiOjE2NTIxOTg5NDF9.AkpFM_-Fz0DcZXSnVKq_4CHjyz4dLnkjaepkcq5Qp20'
  },
  methods: {
    showHide () {
      if (this.type === 'password') {
        this.type = 'text'
        this.show_hide = 'hide'
      } else if (this.type === 'text') {
        this.type = 'password'
        this.show_hide = 'show'
      }
    },
    C_showHide () {
      if (this.C_type === 'password') {
        this.C_type = 'text'
        this.C_show_hide = 'hide'
      } else if (this.C_type === 'text') {
        this.C_type = 'password'
        this.C_show_hide = 'show'
      }
    },
    pin_showHide () {
      if (this.pin_type === 'password') {
        this.pin_type = 'text'
        this.pin_show_hide = 'hide'
      } else if (this.pin_type === 'text') {
        this.pin_type = 'password'
        this.pin_show_hide = 'show'
      }
    },
    register () {
      this.accountCreated = true
      this.loading = true
      this.$axios.$post('/register', {
        firstname: this.first_name,
        lastname: this.last_name,
        email: this.email,
        password: this.password,
        pin: this.pin,
        number: this.phone_number
      }, {
        headers: {
          Authorization: `Bearer ${this.publicToken}`
        }
      }).then((response) => {
        // console.log(response)
        this.loading = false
        if (!response.error) {
          // console.log(response)
          this.$toast.success(response.statusText)
          Cookies.set('token', response.data.token)
          Cookies.set('id', response.data.id)
          Cookies.set('first_name', this.first_name)
          Cookies.set('last_name', this.last_name)
          Cookies.set('email', this.email)
          this.accountCreated = true
          // this.$router.push('/')
        } else {
          this.$toast.error(response.errorMsg)
        }
      }).catch((onrejected) => {
        // console.log(onrejected)
        this.loading = false
        if (onrejected.error) {
          // this.error = onrejected.statusText
          this.$toast.error(onrejected.errorMsg)
        }
      })
      // this.accountCreated = true
    }
  }
}
</script>

<style scoped>
* {
  font-family: 'Poppins', sans-serif;
  color: #454545;
}

.modal-backdrop {
  background-image: url('assets/img/login-background.jpg');
  background-size: cover;
  z-index: 7;
  position: fixed;
  overflow: auto;
  height: 100%;
  /* display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center; */
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  /* background-color: rgba(24, 18, 46, 0.8); */
}

.top-side {
  display: flex;
  justify-content: space-between;
  /* align-items: center; */
  padding: 5rem;
  width: 100%;
  /* flex-direction: column; */
}

.lhs {
  flex-basis: 50%;
}

.rhs {
  flex-basis: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal {
  padding: 50px;
  padding-top: 70px;
  /* margin-top: 1rem; */
  background-color: white;
  height: fit-content;
  align-items: center;
  width: 85%;
  border-radius: 20px;
  overflow-y: auto;
  padding-bottom: 50px;
}

.logo {
  width: 17%;
  /* margin-top: 1.5rem; */
}

.logo img {
  width: 100%;
}

.title {
  font-size: 24px;
  font-weight: 600;
  text-align: center;
}

.sub-title {
  font-size: 14px;
  text-align: center;
  margin-top: 10px;
}

.form {
  width: 90%;
  margin: auto;
  margin-top: 30px;
}

.input-container {
  margin-bottom: 20px;
}

.input-div {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
}

.input-box {
  width: 48%;
}

::placeholder {
  font-size: 14px;
}

.label {
  color: #042538;
  font-size: 14px;
  margin-bottom: 8px;
}

input {
  height: 50px;
  width: 100%;
  border-radius: 5px;
  border: 1px solid #C4C4C4;
  padding: 0 20px;
  outline: none;
}

.password-input input {
  border: none;
  /* position: relative; */
  /* bottom: 10px; */
  padding: 0;
  width: 100%;
  height: 20px;
  font-size: 15px;
  outline: none;
  /* padding: 0 20px; */
}

.password-input {
  display: flex;
  align-items: center;
  border: 1px solid #C4C4C4;
  border-radius: 5px;
  width: 100%;
  height: 50px;
  outline: none;
  padding: 0 20px;
  margin-top: 10px;
}

.show-hide {
  opacity: 0.5;
  cursor: pointer;
  font-size: 14px;
}

.forgot-pass {
  color: #5C07A3;
  margin-top: 10px;
  font-size: 14px;
  text-align: right;
  font-weight: 500;
  cursor: pointer;
}

.btn {
  display: flex;
  justify-content: center;
}

.btn button {
  width: 60%;
  height: 50px;
  background-color: #5C07A3;
  color: #fff;
  border: none;
  outline: none;
  cursor: pointer;
  border-radius: 5px;
  margin-top: 20px;
}

.text {
  margin-top: 40px;
  text-align: center;
  font-size: 14px;
}

.create-acct {
  text-align: center;
  font-size: 14px;
  color: #5C07A3;
  margin-top: 6px;
  font-weight: 500;
}

.link {
  color: rgba(255, 255, 255, 0.535);
  margin-bottom: 10px;
  font-size: 12px;
}

@media only screen and (max-width: 900px) {
  .top-side {
    width: 80%;
  }

  .form {
    width: 100%;
  }

}

@media only screen and (max-width: 500px) {
  .logo {
    width: 25%;
    margin-top: 1rem;
  }

  .top-side {
    width: 90%;
    margin-bottom: 50px;
  }

  .modal {
    padding: 30px;
    padding-top: 50px;
    margin-top: 1rem;
  }

  .title {
    font-size: 20px;
  }

  .sub-title {
    font-size: 14px;
  }

  .form {
    width: 100%;
  }

  .label {
    font-size: 12px;
  }

  ::placeholder {
    font-size: 12px;
  }

  .show-hide {
    font-size: 12px;
  }

  .create-acct {
    font-size: 12px;
  }

  .text {
    font-size: 12px;
  }

  .btn button {
    font-size: 14px;
  }

}

</style>
