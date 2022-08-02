<template>
  <div class="container">
    <div class="page-top">
      <p class="page-title">
        SETTINGS
      </p>
      <p class="log-out">
        LOG OUT
      </p>
    </div>
    <hr class="grey-line">
    <div class="inner">
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
      <div v-if="activeTab == 'my-account'" class="tab-1">
        <div class="account-box">
          <p class="head">
            Change Account Details
          </p>
          <!-- <p class="sub-head">
            Automate notifications and provide support through our omni-channel SMS API
          </p> -->
          <div class="input-box">
            <p class="label">
              First Name
            </p>
            <input id="" v-model="first_name" type="text" name="name">
          </div>
          <div class="input-box">
            <p class="label">
              Last Name
            </p>
            <input id="" v-model="last_name" type="text" name="name">
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
          <!-- <p class="sub-head">
            Automate notifications and provide support through our omni-channel SMS API
          </p> -->
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
  </div>
</template>

<script>
export default {
  layout: 'MainLayout',
  data () {
    return {
      activeTab: 'my-account',
      first_name: '',
      last_name: '',
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
    }
  }
}
</script>

<style scoped>
.container {
  padding: 50px 5rem;
}

.page-top {
  display: flex;
  justify-content: space-between;
}

.log-out {
  color: #de0000;
  font-size: 17px;
  font-weight: 600;
}

.inner {
  width: 35%;
  margin: auto;
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

.account-box {
  width: 100%;
  /* margin: auto; */
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
