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
        <input v-model="nationality" type="text" class="input" placeholder="Nationality">
      </div>
    </div>
    <div class="row">
      <div class="input-ctn">
        <p class="label">
          State of Origin
        </p>
        <input v-model="state" type="text" class="input" placeholder="State of Origin">
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
  </div>
</template>

<script>
export default {

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
  padding-left: 15px;
}

::placeholder {
  font-size: 14px;
  color: #818181;
}
</style>
