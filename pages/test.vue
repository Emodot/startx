<template>
  <div class="container">
    <div class="tabs-container">
      <div class="inner-tab">
        <div
          :class="activeTab.includes('my-account') ? 'active' : 'inactive'"
          class="tab"
          @click="activeTab = 'my-account'"
        >
          My Account
        </div>
        <div
          :class="activeTab.includes('security') ? 'active' : 'inactive'"
          class="tab"
          @click="activeTab = 'security'"
        >
          Security
        </div>
      </div>
      <p class="log-out" @click="logout()">
        Log Out
      </p>
    </div>
    <div v-if="activeTab == 'my-account'" class="tab-1">
      <div class="account-box">
        <p class="head">
          Change Account Details
        </p>
        <p class="sub-head">
          Automate notifications and provide support through our omni-channel SMS API
        </p>
        <div class="input-box">
          <p class="label">
            Full Name
          </p>
          <input id="" v-model="fullname" type="text" name="name">
        </div>
        <div class="input-box">
          <p class="label">
            Email Address
          </p>
          <input id="" v-model="email" type="email" name="email" disabled>
        </div>
        <div class="input-box">
          <p class="label">
            Phone Number
          </p>
          <input id="" v-model="phonenumber" type="text" name="phonenumber">
        </div>
        <button v-if="acctLoading">
          <Loader />
        </button>
        <button v-else @click="changeAcctDetails()">
          Save Changes
        </button>
      </div>
    </div>
    <div v-if="activeTab == 'security'" class="tab-1">
      <div class="account-box">
        <p class="head">
          Keep your account protected
        </p>
        <p class="sub-head">
          Automate notifications and provide support through our omni-channel SMS API
        </p>
        <div class="input-box">
          <p class="label">
            Enter Current Password
          </p>
          <div class="password-input">
            <input v-model="currentPassword" :type="type">
            <p class="show-hide" @click="showHide()">
              {{ show_hide }}
            </p>
          </div>
        </div>
        <div class="input-box">
          <p class="label">
            New Password
          </p>
          <div class="password-input">
            <input v-model="newPassword" :type="N_type">
            <p class="show-hide" @click="N_showHide()">
              {{ N_show_hide }}
            </p>
          </div>
        </div>
        <div class="input-box">
          <p class="label">
            Confirm New Password
          </p>
          <div class="password-input">
            <input v-model="confirmPassword" :type="C_type">
            <p class="show-hide" @click="C_showHide()">
              {{ C_show_hide }}
            </p>
          </div>
        </div>
        <button v-if="secLoading">
          <Loader />
        </button>
        <button v-else @click="changePassword()">
          Save Changes
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import Cookies from 'js-cookie'
export default {
  layout: 'MainLayout',
  data () {
    return {
      activeTab: 'my-account',
      fullname: '',
      email: '',
      phonenumber: '',
      currentPassword: '',
      newPassword: '',
      confirmPassword: '',
      type: 'password',
      show_hide: 'show',
      C_type: 'password',
      C_show_hide: 'show',
      N_type: 'password',
      N_show_hide: 'show',
      secLoading: false,
      acctLoading: false
    }
  },
  created () {
    this.getUserDetails()
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
    N_showHide () {
      if (this.N_type === 'password') {
        this.N_type = 'text'
        this.N_show_hide = 'hide'
      } else if (this.N_type === 'text') {
        this.N_type = 'password'
        this.N_show_hide = 'show'
      }
    },
    getUserDetails () {
      const getFullname = Cookies.get('fullname')
      this.fullname = getFullname
      const getEmail = Cookies.get('email')
      this.email = getEmail
      const getPhone = Cookies.get('phonenumber')
      this.phonenumber = getPhone
    },
    logout () {
      this.$store.commit('setToken')
      Cookies.set('token', '')
      Cookies.set('fullname', 'undefined')
      Cookies.set('email', '')
      Cookies.set('phonenumber', '')
      Cookies.set('userId', '')
      this.$router.push('/signin')
      this.$toaster.showToast({
        content: 'Logged Out',
        state: 'success'
      })
    },
    async changeAcctDetails () {
      this.acctLoading = true
      try {
        const changeAcctPromise = await fetch(`${this.$store.state.baseUrl}/user/${Cookies.get('userId')}`,
          {
            method: 'PATCH',
            headers: {
              'Content-Type': 'application/json',
              Authorization: `Bearer ${Cookies.get('token')}`
            },
            body: JSON.stringify({
              fullname: this.fullname,
              phone: this.phonenumber
            })
          })
        const changeAcctJson = changeAcctPromise.json()
        changeAcctJson.then((response) => {
          this.acctLoading = false
          if (!response.error) {
            Cookies.set('fullname', response.data.fullname)
            Cookies.set('phonenumber', response.data.phone)
            this.$toaster.showToast({
              content: response.message,
              state: 'success'
            })
            window.location.reload()
          } else {
            this.$toaster.showToast({
              content: response.message,
              state: 'error'
            })
          }
        })
      } catch (error) {
        this.acctLoading = false
      }
    },
    async changePassword () {
      this.secLoading = true
      if (this.newPassword !== this.confirmPassword) {
        this.$toaster.showToast({
          content: 'Confirm Password not correct',
          state: 'error'
        })
        this.secLoading = false
      } else {
        try {
          const changePasswordPromise = await fetch(this.$store.state.baseUrl + '/user/change_password/',
            {
              method: 'POST',
              headers: {
                'Content-Type': 'application/json',
                Authorization: `Bearer ${Cookies.get('token')}`
              },
              body: JSON.stringify({
                oldpassword: this.currentPassword,
                newpassword: this.newPassword
              })
            })
          const changePasswordJson = changePasswordPromise.json()
          changePasswordJson.then((response) => {
            this.secLoading = false
            if (!response.error) {
              this.$toaster.showToast({
                content: response.message,
                state: 'success'
              })
            } else {
              this.$toaster.showToast({
                content: response.message,
                state: 'error'
              })
            }
          })
        } catch (error) {
          this.secLoading = false
        }
      }
    }
  }
}
</script>

<style scoped>

.tabs-container {
  display: flex;
  justify-content: space-between;
  margin: 20px 0;
  border-bottom: 1px solid #75759e1e;
}

.tabs-container .active {
  color: #0082FA !important;
  border-bottom: 3px solid #0082FA;
}

.inner-tab {
  display: flex;
}

.tabs-container .tab{
  padding: 15px;
  cursor: pointer;
  margin-right: 70px;
  color: #75759ead;
}

.tab-1 {
  padding-top: 20px;
}

.log-out {
  padding: 15px;
  color: red;
  font-weight: 700;
  cursor: pointer;
}

.account-box {
  width: 40%;
  background-color: white;
  padding: 40px 70px;
}

.head {
  color: #414B58;
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 20px;
  line-height: 25px;
}

.sub-head {
  color: #758396;
  line-height: 30px;
  padding-bottom: 20px;
}

.input-box {
  margin: 20px 0;
}

.label {
  font-size: 14px;
  margin-bottom: 10px;
}

input {
  border: 1px solid #4b545abe;
  width: 100%;
  height: 50px;
  padding: 0 15px;
  border-radius: 5px;
  outline: none;
}

.password-input input {
  border: none;
  /* position: relative; */
  /* bottom: 10px; */
  width: 100%;
  height: 20px;
  font-size: 15px;
  outline: none;
  /* padding: 0 20px; */
}

.password-input {
  display: flex;
  align-items: center;
  border: 1px solid #4b545abe;
  border-radius: 5px;
  /* position: relative; */
  /* bottom: 10px; */
  width: 100%;
  height: 50px;
  /* font-size: 15px; */
  outline: none;
  padding-right: 20px;
}

.show-hide {
  opacity: 0.5;
  cursor: pointer;
  font-size: 15px;
}

.account-box button {
  color: white;
  background-color: #0082FA;
  border-radius: 5px;
  padding: 18px 50px;
  width: 250px;
  border: none;
  margin-top: 20px;
}

@media only screen and (max-width: 900px) {
  .account-box {
    width: 70%;
  }
}

@media only screen and (max-width: 500px) {
.tabs-container .tab{
  font-size: 13px;
  margin-right: 0;
}

.account-box {
  width: 100%;
  padding: 20px;
}

}
</style>
