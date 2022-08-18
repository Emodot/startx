<template>
  <div class="modal-backdrop-2 reveal">
    <div class="modal-2">
      <div class="modal-icon">
        <svg width="84" height="84" viewBox="0 0 84 84" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M3.5 42C3.5 20.737 20.737 3.5 42 3.5C63.263 3.5 80.5 20.737 80.5 42C80.5 63.263 63.263 80.5 42 80.5C20.737 80.5 3.5 63.263 3.5 42Z" fill="#5C07A3" />
          <path fill-rule="evenodd" clip-rule="evenodd" d="M60.5873 28.1503C61.9542 29.5171 61.9542 31.7332 60.5873 33.1L38.8624 55.85C37.4956 57.2168 35.2795 57.2168 33.9127 55.85L23.4127 45.35C22.0459 43.9832 22.0459 41.7671 23.4127 40.4003C24.7795 39.0334 26.9956 39.0334 28.3624 40.4003L36.3876 48.4254L55.6376 28.1503C57.0044 26.7834 59.2205 26.7834 60.5873 28.1503Z" fill="white" />
        </svg>
      </div>
      <h1 class="title">
        Password Changed!
      </h1>
      <p class="sub-title">
        You have successfully created a new Password
      </p>
      <div class="form">
        <div class="btn">
          <button @click="$router.push('/')">
            Dashboard
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    actionData: {
      type: String,
      default: ''
    },
    page: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
    }
  }
}
</script>

<style scoped>
* {
  font-family: 'Poppins', sans-serif;
  color: #454545;
}
.modal-backdrop-2 {
  z-index: 7;
  position: fixed;
  overflow: auto;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(24, 18, 46, 0.8);
}

.modal-2 {
  /* margin-top: 5%; */
  background-color: white;
  width: 32%;
  height: fit-content;
  align-items: center;
  border-radius: 20px;
  overflow-y: auto;
  padding-bottom: 5rem;
}

.modal-icon {
  text-align: center;
  margin-top: 40px;
  margin-bottom: 20px;
}

.modal-icon img {
  width: 80px;
}

::placeholder {
  font-size: 14px;
}

.title {
  font-size: 24px;
  font-weight: 600;
  text-align: center;
  margin-top: 30px;
}

.sub-title {
  font-size: 14px;
  text-align: center;
  width: 60%;
  margin: auto;
  margin-top: 20px;
}

.span-account {
  font-size: 14px;
  color: #5C07A3;
  cursor: pointer;
  /* text-align: center;
  width: 60%;
  margin: auto;
  margin-top: 10px; */
}

.form {
  width: 75%;
  margin: auto;
  margin-top: 30px;
}

.input-container {
  margin-bottom: 20px;
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

.btn {
  display: flex;
  justify-content: center;
}

.btn button {
  width: 70%;
  height: 50px;
  background-color: #5d07a337;
  border: 2px solid #5C07A3;
  color: #5C07A3;
  outline: none;
  cursor: pointer;
  border-radius: 5px;
  margin-top: 20px;
}

.text {
  margin-top: 20px;
  text-align: center;
  font-size: 14px;
  cursor: pointer;
}

@media only screen and (max-width: 900px) {
  .modal-2 {
    width: 70%;
  }
}

@media only screen and (max-width: 500px) {

  .modal-2 {
    width: 90%;
    padding: 30px;
    /* padding-top: 50px; */
    margin-top: 1rem;
  }

  .modal-icon {
    margin-top: 0;
  }

  .title {
    font-size: 20px;
  }

  .sub-title {
    font-size: 14px;
    width: 100%;
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

  .text {
    font-size: 12px;
  }

  .btn button {
    font-size: 14px;
  }

}

</style>
