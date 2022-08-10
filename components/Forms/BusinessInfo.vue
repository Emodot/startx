<template>
  <div class="ctn">
    <p class="content-title">
      Educational Information
    </p>
    <hr class="content-line">
    <div>
      <div class="row">
        <div class="input-ctn">
          <p class="label">
            Institution Name
          </p>
          <input v-model="institution" type="text" class="input" placeholder="Institution Name">
        </div>
        <div class="input-ctn">
          <p class="label">
            Date Started
          </p>
          <input v-model="date_started" type="date" class="input" placeholder="Date Started">
        </div>
        <div class="input-ctn">
          <p class="label">
            Date Ended
          </p>
          <input v-model="date_ended" type="date" class="input" placeholder="Date Ended">
        </div>
      </div>
      <div class="row">
        <div class="input-ctn">
          <p class="label">
            Degree
          </p>
          <div class="form-select">
            <select v-model="degree" required>
              <option value="">
                Select Degree
              </option>
              <option value="lagos">
                B.Tech
              </option>
              <option value="abuja">
                B.SC
              </option>
            </select>
            <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M14.625 6.75L9 12.375L3.375 6.75" stroke="#818181" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
          </div>
        </div>
        <div class="con">
          <p class="label no-show">
            D
          </p>
          <button class="add-btn">
            <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M2.1875 7H11.8125" stroke="#5C07A3" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
              <path d="M7 2.1875V11.8125" stroke="#5C07A3" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
            Add New Institution
          </button>
        </div>
        <div class="input-ctn" />
      </div>
    </div>
    <p class="content-title">
      Coporate Experience
    </p>
    <hr class="content-line">
    <div>
      <div class="row">
        <div class="input-ctn">
          <p class="label">
            Company Name
          </p>
          <input v-model="company" type="text" class="input" placeholder="Company Name">
        </div>
        <div class="input-ctn">
          <p class="label">
            Date Started
          </p>
          <input v-model="c_date_started" type="date" class="input" placeholder="Date Started">
        </div>
        <div class="input-ctn">
          <p class="label">
            Date Ended
          </p>
          <input v-model="c_date_ended" type="date" class="input" placeholder="Date Ended">
        </div>
      </div>
      <div class="row">
        <div class="input-ctn">
          <p class="label">
            Position
          </p>
          <input v-model="position" type="text" class="input" placeholder="Position">
        </div>
        <div class="con">
          <p class="label no-show">
            D
          </p>
          <button class="add-btn">
            <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M2.1875 7H11.8125" stroke="#5C07A3" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
              <path d="M7 2.1875V11.8125" stroke="#5C07A3" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
            Add New Experience
          </button>
        </div>
        <div class="input-ctn" />
      </div>
    </div>
    <p class="content-title">
      Licenses &amp; certifications
    </p>
    <hr class="content-line">
    <div>
      <div class="row">
        <div class="input-ctn">
          <p class="label">
            Name
          </p>
          <input v-model="certificate" type="text" class="input" placeholder="Certificate Name">
        </div>
        <div class="input-ctn">
          <p class="label">
            Issuing Organization
          </p>
          <input v-model="organization" type="text" class="input" placeholder="Issuing Organization">
        </div>
        <div class="input-ctn">
          <p class="label">
            Issue Date
          </p>
          <input v-model="issue_date" type="date" class="input" placeholder="Issue Date">
        </div>
      </div>
      <div class="row">
        <div class="input-ctn">
          <p class="label">
            Certificate ID
          </p>
          <input v-model="certificate_id" type="text" class="input" placeholder="Certificate ID">
        </div>
        <div class="input-ctn">
          <p class="label">
            Credential URL
          </p>
          <input v-model="certificate_url" type="text" class="input" placeholder="Credential URL">
        </div>
        <div class="con">
          <p class="label no-show">
            D
          </p>
          <button class="add-btn">
            <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M2.1875 7H11.8125" stroke="#5C07A3" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
              <path d="M7 2.1875V11.8125" stroke="#5C07A3" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
            Add New Certification
          </button>
        </div>
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
      institution: '',
      date_started: '',
      date_ended: '',
      degree: '',
      faceBook: '',
      hobbies: '',
      skills: ''
    }
  }
}
</script>

<style scoped>
.content-title {
  color: #060D49;
  font-size: 15px;
}

.content-line {
  border: none;
  border-top: 1px solid #E7E7E7;
  margin-top: 20px;
  margin-bottom: 30px;
}

.no-show {
  color: transparent !important;
}

.con {
  flex-basis: 30%;
}

.add-btn {
  color: #5C07A3;
  background-color: transparent;
  border: 1px solid #5C07A3;
  font-size: 14px;
  border-radius: 5px;
  padding: 15px 25px;
  outline: none;
  cursor: pointer;
}

.add-btn svg {
  margin-right: 10px;
}

.row {
  display: flex;
  justify-content: space-between;
  /* align-items: flex-end; */
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

.text-area-ctn {
  width: 100%;
}

textarea {
  outline: none;
  width: 100%;
  padding: 20px;
}

@media screen and (max-width: 600px) {
  .row {
    flex-direction: column;
    margin-bottom: 0;
  }

  .input-ctn {
    margin-bottom: 20px;
  }

  .bottom-btn {
    margin-top: 2rem;
  }

  .no-show {
    margin-bottom: 0;
  }
}
</style>
