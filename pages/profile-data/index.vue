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
            <button class="edit-btn" @click="$router.push('/profile-data/edit')">
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
        <!-- Social Media Information -->
        <div class="personal">
          <p class="content-title">
            Social Media Information
          </p>
          <hr class="content-line">
          <div class="row-ctn">
            <div class="box">
              <p class="box-title">
                Instagram
              </p>
              <p class="box-text">
                @emayedavid
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Twitter
              </p>
              <p class="box-text">
                @davidemaye
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                LinkedIn
              </p>
              <p class="box-text">
                David Emaye
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Facebook
              </p>
              <p class="box-text">
                Emaye David
              </p>
            </div>
          </div>
        </div>
        <!-- Business Information - Educational Information -->
        <div class="personal">
          <p class="content-title">
            Business Information - Educational Information
          </p>
          <hr class="content-line">
          <div class="row-ctn more-data">
            <div class="box">
              <p class="box-title">
                Institution Name
              </p>
              <p class="box-text">
                Ondo State University of Science and Technology
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Date Started
              </p>
              <p class="box-text">
                15th, May 2008
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Date Ended
              </p>
              <p class="box-text">
                15th, May 2010
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Degree
              </p>
              <p class="box-text">
                B-Tech
              </p>
            </div>
          </div>
          <hr class="data-line">
          <div class="row-ctn more-data">
            <div class="box">
              <p class="box-title">
                Institution Name
              </p>
              <p class="box-text">
                Ondo State University of Science and Technology
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Date Started
              </p>
              <p class="box-text">
                15th, May 2008
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Date Ended
              </p>
              <p class="box-text">
                15th, May 2010
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Degree
              </p>
              <p class="box-text">
                B-Tech
              </p>
            </div>
          </div>
        </div>
        <!-- Business Information - Coporate Experience -->
        <div class="personal">
          <p class="content-title">
            Business Information - Coporate Experience
          </p>
          <hr class="content-line">
          <div class="row-ctn more-data">
            <div class="box">
              <p class="box-title">
                Comapny Name
              </p>
              <p class="box-text">
                Acumen Digital
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Date Started
              </p>
              <p class="box-text">
                15th, May 2008
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Date Ended
              </p>
              <p class="box-text">
                15th, May 2010
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Position
              </p>
              <p class="box-text">
                Software Engineer
              </p>
            </div>
          </div>
          <hr class="data-line">
          <div class="row-ctn more-data">
            <div class="box">
              <p class="box-title">
                Comapny Name
              </p>
              <p class="box-text">
                Acumen Digital
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Date Started
              </p>
              <p class="box-text">
                15th, May 2008
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Date Ended
              </p>
              <p class="box-text">
                15th, May 2010
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Position
              </p>
              <p class="box-text">
                Software Engineer
              </p>
            </div>
          </div>
        </div>
        <!-- Business Information - Licenses & certifications -->
        <div class="personal">
          <p class="content-title">
            Business Information - Licenses &amp; certifications
          </p>
          <hr class="content-line">
          <div class="row-ctn more-data">
            <div class="box">
              <p class="box-title">
                Name
              </p>
              <p class="box-text">
                The Fundamentals of Digital Marketing
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Issuing Organization
              </p>
              <p class="box-text">
                Google
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Issue Date
              </p>
              <p class="box-text">
                15th, May 2010
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Certificate ID
              </p>
              <p class="box-text">
                HDJF8IO3K39
              </p>
            </div>
          </div>
          <div class="box-ex">
            <p class="box-title">
              Credential URL
            </p>
            <p class="box-text">
              https://learndigital.withgoogle.com/digitalgarage/course/digital-marketing
            </p>
          </div>
          <hr class="data-line">
          <div class="row-ctn more-data">
            <div class="box">
              <p class="box-title">
                Name
              </p>
              <p class="box-text">
                The Fundamentals of Digital Marketing
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Issuing Organization
              </p>
              <p class="box-text">
                Google
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Issue Date
              </p>
              <p class="box-text">
                15th, May 2010
              </p>
            </div>
            <div class="box">
              <p class="box-title">
                Certificate ID
              </p>
              <p class="box-text">
                HDJF8IO3K39
              </p>
            </div>
          </div>
          <div class="box-ex">
            <p class="box-title">
              Credential URL
            </p>
            <p class="box-text">
              https://learndigital.withgoogle.com/digitalgarage/course/digital-marketing
            </p>
          </div>
        </div>
        <!-- Other Information -->
        <div class="personal">
          <p class="content-title">
            Other Information
          </p>
          <hr class="content-line">
          <div class="row-ctn">
            <div class="box-ot">
              <p class="box-title">
                Skills
              </p>
              <p class="box-text">
                Ipsum, Dolor, sit, amet, consectetur, lorem
              </p>
            </div>
            <div class="box-ot">
              <p class="box-title">
                Hobbies
              </p>
              <p class="box-text">
                Ipsum, Dolor, sit, amet, consectetur, lorem
              </p>
            </div>
          </div>
          <div class="row-ctn">
            <div class="box-su">
              <p class="box-title">
                Summary About You
              </p>
              <p class="box-text">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce arcu tortor, porta quis cursus id, ultrices a erat. Ut lobortis, nisl nec tempor maximus, lacus enim condimentum lorem, eu hendrerit quam dui ac nulla. Fusce vitae tortor pulvinar, mattis eros et, congue tellus. Nullam eget iaculis libero. Nulla odio ligula, ornare varius gravida malesuada, sollicitudin eu urna. Fusce ultricies nunc tortor, ut finibus leo fringilla ut. Nunc nec lacinia purus, vel
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
  margin-bottom: 30px;
}

.data-line {
  border: none;
  border-top: 2px solid #E7E7E7;
  width: 50%;
  margin: 20px 0;
}

.row-ctn {
  display: flex;
  margin-bottom: 30px;
}

.more-data {
  margin-bottom: 0;
}

.box {
  flex-basis: 25%;
  padding-right: 20px;
}

.box-ot {
  flex-basis: 50%;
  padding-right: 20px;
}

.box-su {
  flex-basis: 100%;
  padding-right: 20px;
}

.box-ex {
  margin-top: 20px;
  margin-bottom: 30px;
}

.box-title {
  font-size: 13px;
  color: #75759E;
}

.box-text {
  /* font-weight: 13px; */
  margin-top: 10px;
  line-height: 20px;
  color: #000000;
}

@media screen and (max-width: 600px) {
  .container {
    padding: 20px;
  }

  .content-box {
    width: 100%;
    padding: 20px;
  }

  .top-fullname {
    font-size: 18px;
  }

  .top-email {
    font-size: 13px;
    margin-top: 7px;
  }

  .edit-btn {
    font-size: 13px;
    padding: 10px 15px;
  }

  .edit-btn svg {
    margin-right: 6px;
    width: 12px;
  }

  .personal {
    margin-top: 3rem;
  }

  .content-line {
    margin-top: 10px;
    margin-bottom: 20px;
  }

  .data-line  {
    margin-top: 0;
  }

  .row-ctn {
    margin-bottom: 0;
    flex-wrap: wrap;
  }

  .box {
    flex-basis: 50%;
    margin-bottom: 20px;
  }

  .box-text {
    font-size: 15px;
    word-break: break-word;
  }

  .box-ot {
    margin-bottom: 20px;
  }
}
</style>
