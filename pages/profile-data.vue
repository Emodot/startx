<template>
  <div class="container">
    <p class="page-title">
      PROFILE DATA
    </p>
    <hr class="grey-line">
    <div class="inner">
      <div class="content-box">
        <div class="content-top">
          <div class="con-lhs">
            <p class="top-fullname">
              David Emaye
            </p>
            <p class="top-email">
              emayeodavid@gmail.com
            </p>
          </div>
          <div class="con-rhs">
            <button class="edit-btn">
              <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M11.4005 0C11.2061 0 11.0039 0.077767 10.8562 0.225524L9.43304 1.64866L12.3493 4.56492L13.7724 3.14179C14.0757 2.83849 14.0757 2.34856 13.7724 2.04527L11.9527 0.225524C11.7972 0.0699903 11.6027 0 11.4005 0ZM8.60103 4.68159L9.31648 5.39704L2.2708 12.4427H1.55534V11.7273L8.60103 4.68159ZM0 11.0817L8.60103 2.48072L11.5173 5.39698L2.91626 13.998H0V11.0817Z" fill="white" />
              </svg>
              Edit Profile Data
            </button>
          </div>
        </div>

        <!-- Personal Information -->
        <div class="personal">
          <p class="content-title">
            Personal Information
          </p>
          <hr class="content-line">
          <div class="row-ctn">
            <div class="box">
              <p class="box-title">
                First Name
              </p>
              <p class="box-text">
                David
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Middle Name
              </p>
              <p class="box-text">
                Oluwadamilare
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Last Name
              </p>
              <p class="box-text">
                Emaye
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Email Address
              </p>
              <p class="box-text">
                emayeodavid@gmail.com
              </p>
            </div>
          </div>
          <div class="row-ctn">
            <div class="box">
              <p class="box-title">
                Phone Number
              </p>
              <p class="box-text">
                +234 810 8551 935
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Date of Birth
              </p>
              <p class="box-text">
                15th, May 2015
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Age
              </p>
              <p class="box-text">
                15
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Languages
              </p>
              <p class="box-text">
                English, Yoruba
              </p>
            </div>
          </div>
          <div class="row-ctn">
            <div class="box">
              <p class="box-title">
                Nationality
              </p>
              <p class="box-text">
                Nigerian
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                State of Origin
              </p>
              <p class="box-text">
                Ondo
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                State of Residence
              </p>
              <p class="box-text">
                Lagos
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Residential Address
              </p>
              <p class="box-text">
                15, Balogun, Ikeja
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'MainLayout',
  data () {
    return {}
  }
}
</script>

<style scoped>
.container {
  padding: 50px 5rem;
}

.content-box {
  width: 80%;
  padding: 40px;
  background-color: #ffffff;
}

.content-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.top-fullname {
  font-size: 24px;
  font-weight: 600;
}

.top-email {
  font-size: 15px;
  margin-top: 15px;
  color: rgba(0, 0, 0, 0.500);
}

.edit-btn {
  color: #fff;
  background-color: #5C07A3;
  border: none;
  font-size: 14px;
  border-radius: 5px;
  padding: 15px 25px;
  cursor: pointer;
}

.edit-btn svg {
  margin-right: 10px;
}

.personal {
  margin-top: 5rem;
}

.content-title {
  color: #A2ABAA;
  font-size: 14px;
}

.content-line {
  border: none;
  border-top: 1px solid #E7E7E7;
  margin-top: 20px;
  margin-bottom: 40px;
}

.row-ctn {
  display: flex;
  margin-bottom: 30px;
}

.box {
  flex-basis: 25%;
  padding-right: 20px;
}

.box-title {
  font-size: 13px;
  color: #75759E;
}

.box-text {
  /* font-weight: 13px; */
  margin-top: 10px;
  color: #000000;
}
</style>
