<template>
  <div class="ctn">
    <div class="row">
      <div class="input-ctn">
        <p class="label">
          First Name
        </p>
        <input v-model="first_name" type="text" class="input" placeholder="First Name">
      </div>
      <div class="input-ctn">
        <p class="label">
          Middle Name
        </p>
        <input v-model="middle_name" type="text" class="input" placeholder="Middle Name">
      </div>
      <div class="input-ctn">
        <p class="label">
          Last Name
        </p>
        <input v-model="last_name" type="text" class="input" placeholder="Last Name">
      </div>
    </div>
    <div class="row">
      <div class="input-ctn">
        <p class="label">
          Email Address
        </p>
        <input v-model="email" type="text" class="input" placeholder="Email Address">
      </div>
      <div class="input-ctn">
        <p class="label">
          Phone Number
        </p>
        <input v-model="phone" type="text" class="input" placeholder="Phone Number">
      </div>
      <div class="input-ctn">
        <p class="label">
          Date of Birth
        </p>
        <input v-model="dob" type="date" class="input" placeholder="Date of Birth">
      </div>
    </div>
    <div class="row">
      <div class="input-ctn">
        <p class="label">
          Age
        </p>
        <input v-model="age" type="text" class="input" placeholder="Age">
      </div>
      <div class="input-ctn">
        <p class="label">
          Languages
        </p>
        <input v-model="languages" type="text" class="input" placeholder="Languages">
      </div>
      <div class="input-ctn">
        <p class="label">
          Nationality
        </p>
        <div class="form-select">
          <select v-model="nationality" required>
            <option value="">
              Please Select
            </option>
            <option value="nigerian">
              Nigerian
            </option>
            <option value="abuja">
              Abuja
            </option>
          </select>
          <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M14.625 6.75L9 12.375L3.375 6.75" stroke="#818181" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
          </svg>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="input-ctn">
        <p class="label">
          State of Origin
        </p>
        <div class="form-select">
          <select v-model="state_origin" required>
            <option value="">
              Please Select
            </option>
            <option value="lagos">
              Lagos
            </option>
            <option value="abuja">
              Abuja
            </option>
          </select>
          <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M14.625 6.75L9 12.375L3.375 6.75" stroke="#818181" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
          </svg>
        </div>
      </div>
      <div class="input-ctn">
        <p class="label">
          State of Residence
        </p>
        <div class="form-select">
          <select v-model="state_residence" required>
            <option value="">
              Please Select
            </option>
            <option value="lagos">
              Lagos
            </option>
            <option value="abuja">
              Abuja
            </option>
          </select>
          <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M14.625 6.75L9 12.375L3.375 6.75" stroke="#818181" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
          </svg>
        </div>
      </div>
      <div class="input-ctn">
        <p class="label">
          Residential Address
        </p>
        <input v-model="residential_address" type="text" class="input" placeholder="Residential Address">
      </div>
    </div>
    <div class="bottom-btn">
      <button>Save &amp; Continue</button>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      first_name: '',
      last_name: '',
      middle_name: '',
      email: '',
      phone: '',
      dob: '',
      languages: '',
      nationality: '',
      state_residence: '',
      state_origin: '',
      residence_address: '',
      age: ''
    }
  }
}
</script>

<style scoped>
.row {
  display: flex;
  justify-content: space-between;
  width: 100%;
  margin-bottom: 35px;
}

.input-ctn {
  flex-basis: 30%;
}

.label {
  color: rgba(0, 0, 0, 0.500);
  margin-bottom: 13px;
  font-size: 14px;
}

.input {
  height: 50px;
  width: 100%;
  border: 1px solid #B4B4B4;
  outline: none;
  border-radius: 3px;
  padding: 0 15px;
}

::placeholder {
  font-size: 14px;
  color: #818181;
}

.form-select {
  position: relative;
}
.form-select select {
  display: block;
  border: 1px solid #B4B4B4;
  border-radius: 3px;
  display: flex;
  justify-content: space-between;
  height: 50px;
  color: #818181;
  padding: 0 16px;
  width: 100%;
  appearance: none;
  -moz-appearance: none;
  -webkit-appearance: none;
  margin-top: 10px;
  margin-bottom: 10px;
  outline: none;
  font-size: 14px;
}
.form-select svg {
  position: absolute;
  top: 15px;
  left: 90%;
}

.bottom-btn {
  display: flex;
  justify-content: center;
  margin-top: 5rem;
}

.bottom-btn button {
  border: none;
  background-color: #5C07A3;
  height: 50px;
  width: 12rem;
  font-size: 14px;
  color: #fff;
  outline: none;
  border-radius: 20px;
  cursor: pointer;
}
</style>
