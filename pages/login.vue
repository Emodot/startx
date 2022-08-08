<template>
  <div class="modal-backdrop">
    <div class="top-side">
      <div class="lhs">
        <div class="logo">
          <img src="~assets/img/StartX-logo-white.png" alt="">
        </div>
      </div>
      <div class="rhs">
        <div v-if="(resetPass === false && linkSent === false && createPassword === false && passwordCreated === false)" class="modal">
          <h1 class="title">
            Welcome Back!
          </h1>
          <p class="sub-title">
            Login with your account details to continue.
          </p>
          <div class="form">
            <div class="input-container">
              <p class="label">
                Email Address
              </p>
              <input v-model="email" type="email" name="" placeholder="Enter Email Address">
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
              <p class="forgot-pass" @click="resetPass = true">
                Forgot Password?
              </p>
            </div>
            <div class="btn">
              <button v-if="loading">
                <Loader />
              </button>
              <button v-else @click="login()">
                Login
              </button>
            </div>
            <p class="text">
              Not yet a register user?
            </p>
            <NuxtLink to="/register">
              <p class="create-acct">
                Create An Account
              </p>
            </NuxtLink>
          </div>
        </div>
      </div>
    </div>
    <!-- <p class="link">
      www.startx.com
    </p> -->
    <ResetPassword v-if="resetPass" @close-modal="resetPass = false" @sentInst="sentInst" />
    <LinkSent v-if="linkSent" :user-email="userEmail" @set-password="setPassword" />
    <CreatePassword v-if="createPassword" />
    <PasswordCreated v-if="passwordCreated" />
  </div>
</template>

<script>
// import Cookies from 'js-cookie'
import LinkSent from '~/components/Modals/LinkSent.vue'
import ResetPassword from '~/components/Modals/ResetPassword.vue'
import CreatePassword from '~/components/Modals/CreatePassword.vue'
import PasswordCreated from '~/components/Modals/PasswordCreated.vue'
export default {
  components: {
    ResetPassword,
    LinkSent,
    CreatePassword,
    PasswordCreated
  },
  data () {
    return {
      loading: false,
      email: '',
      password: '',
      resetPass: false,
      linkSent: false,
      passwordCreated: false,
      createPassword: false,
      type: 'password',
      show_hide: 'show',
      publicToken: '',
      userEmail: ''
    }
  },
  // created () {
  //   // this.publicToken = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI2MjdhOGUxZDliMjVkMThiZjVhNDRmZWQiLCJpYXQiOjE2NTIxOTg5NDF9.AkpFM_-Fz0DcZXSnVKq_4CHjyz4dLnkjaepkcq5Qp20'
  // },
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
    sentInst (email) {
      this.userEmail = email
      this.resetPass = false
      this.linkSent = true
    },
    setPassword () {
      this.linkSent = false
      this.createPassword = true
    },
    login () {
      this.$router.push('/')
      this.loading = true
      // this.$axios.$post('/login', {
      //   email: this.email,
      //   password: this.password
      // }, {
      //   headers: {
      //     Authorization: `Bearer ${Cookies.get('token')}`
      //   }
      // }).then((response) => {
      //   this.loading = false
      //   // console.log(response)
      //   if (!response.error) {
      //     this.$toast.success(response.statusText)
      //     Cookies.set('token', response.token)
      //     Cookies.set('id', response.id)
      //     this.$router.push('/')
      //   } else {
      //     this.$toast.error(response.errorMsg)
      //   }
      // }).catch((onrejected) => {
      //   // console.log(onrejected)
      //   this.loading = false
      //   if (onrejected.error) {
      //     this.$toast.error(onrejected.errorMsg)
      //   }
      // })
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
  /* margin-top: 3rem; */
  background-color: white;
  height: fit-content;
  align-items: center;
  width: 80%;
  border-radius: 20px;
  overflow-y: auto;
  padding-bottom: 50px;
}

.logo {
  width: 17%;
  /* margin-top: 3rem; */
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
  margin-top: 20px;
}

.form {
  width: 90%;
  margin: auto;
  margin-top: 30px;
}

.input-container {
  margin-bottom: 20px;
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
    width: 70%;
  }

  .form {
    width: 100%;
  }

}

@media only screen and (max-width: 500px) {
  .logo {
    width: 40%;
    margin-top: 3rem;
  }

  .top-side {
    width: 100%;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-bottom: 50px;
    padding: 0;
  }

  .lhs {
    flex-basis: 10%;
    display: flex;
    justify-content: center;
  }

  .rhs {
    flex-basis: 100%;
    width: 90%;
  }

  .modal {
    width: 100%;
    padding: 30px;
    padding-top: 50px;
    margin-top: 2rem;
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

  .forgot-pass {
    font-size: 12px;
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
