<template>
  <div class="ctn">
    <p class="content-title">
      Social Media Information
    </p>
    <hr class="content-line">
    <div class="row">
      <div class="input-ctn">
        <p class="label">
          Instagram
        </p>
        <input v-model="instagram" type="text" class="input" placeholder="@Instagram">
      </div>
      <div class="input-ctn">
        <p class="label">
          Twitter
        </p>
        <input v-model="twitter" type="text" class="input" placeholder="@Twitter">
      </div>
      <div class="input-ctn">
        <p class="label">
          LinkedIn
        </p>
        <input v-model="linkedIn" type="text" class="input" placeholder="LinkedIn">
      </div>
    </div>
    <div class="row">
      <div class="input-ctn">
        <p class="label">
          FaceBook
        </p>
        <input v-model="faceBook" type="text" class="input" placeholder="FaceBook">
      </div>
    </div>
    <p class="content-title">
      Other Information
    </p>
    <hr class="content-line">
    <div class="row">
      <div class="input-ctn">
        <p class="label">
          Skills
        </p>
        <input v-model="skills" type="text" class="input" placeholder="Skills">
      </div>
      <div class="input-ctn">
        <p class="label">
          Hobbies
        </p>
        <input v-model="hobbies" type="text" class="input" placeholder="Hobbies">
      </div>
      <div class="input-ctn" />
    </div>
    <div class="row">
      <div class="text-area-ctn">
        <p class="label">
          Summary About You
        </p>
        <textarea
          id=""
          v-model="summary"
          name=""
          rows="10"
          placeholder="Summary About You..."
        />
      </div>
    </div>
    <div class="bottom-btn">
      <button>Save</button>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      instagram: '',
      twitter: '',
      linkedIn: '',
      faceBook: '',
      summary: '',
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

.text-area-ctn {
  width: 100%;
}

textarea {
  outline: none;
  width: 100%;
  padding: 20px;
}
</style>
