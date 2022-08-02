<template>
  <div class="container">
    <p class="page-title">
      SUBSCRIPTION
    </p>
    <hr class="grey-line">
    <div class="inner">
      <p class="head">
        Lorem ipsum dolor sit amet, consectetur
      </p>
      <p class="sub-head">
        In rutrum nunc sed massa egestas dignissim. Etiam nibh eros, finibus non
      </p>
      <div class="plans">
        <div class="plan">
          <div class="plan-top">
            <p class="plan-name">
              Monthly
            </p>
            <p class="popular">
              Most Popular
            </p>
          </div>
          <p class="points">
            Lorem ipsum dolor sit amet
          </p>
          <p class="points">
            Ipsum dolor sit amet
          </p>
          <p class="points">
            Dolor ipsum  sit amet
          </p>
          <p class="points">
            Amet ipsum dolor sit amet
          </p>
          <p class="points">
            Lorem ipsum dolor sit amet
          </p>
          <div class="price-box">
            <p class="price">
              <span class="naira">₦ </span>4,999 <span class="month">monthly</span>
            </p>
            <div class="price-btn">
              <button>Get Started</button>
            </div>
          </div>
        </div>
        <div class="plan">
          <div class="plan-top">
            <p class="plan-name">
              Monthly
            </p>
            <p class="popular">
              Most Popular
            </p>
          </div>
          <p class="points">
            Lorem ipsum dolor sit amet
          </p>
          <p class="points">
            Ipsum dolor sit amet
          </p>
          <p class="points">
            Dolor ipsum  sit amet
          </p>
          <p class="points">
            Amet ipsum dolor sit amet
          </p>
          <p class="points">
            Lorem ipsum dolor sit amet
          </p>
          <div class="price-box">
            <p class="price">
              <span class="naira">₦ </span>4,999 <span class="month">monthly</span>
            </p>
            <div class="price-btn">
              <button>Get Started</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'MainLayout'

}
</script>

<style scoped>
.container {
  padding: 50px 5rem;
}

.head {
  text-align: center;
  font-size: 30px;
  font-weight: 600;
}

.sub-head {
  text-align: center;
  font-size: 18px;
  margin-top: 20px;
}

.plans {
  margin-top: 5rem;
  display: flex;
}

.plan {
  border: 1px solid #5C07A3;
  width: 22rem;
  border-radius: 20px;
}
.plan-top {
  background-color: #eaedff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 30px;
  height: 5rem;
  margin-bottom: 40px;
  border-radius: 20px 20px 0 0;
}
.plan-name {
  font-size: 28px;
  font-weight: 600;
}

.popular {
  color: #5C07A3;
  font-size: 15px;
  font-weight: 500;
}

.points {
  text-align: center;
  font-weight: 500;
  margin-bottom: 24px;
}

.price-box {
  border: 2px solid #ecefff;
  width: 80%;
  margin: 30px auto;
  padding: 0 22px;
  border-radius: 10px;
}

.price {
  color: #5C07A3;
  font-weight: 600;
  font-size: 45px;
  text-align: center;
  margin: 40px 0;
}

.naira {
  font-size: 18px;
  font-weight: 600;
}

.month {
  color: #74757B;
  font-weight: 600;
}

.price-btn button {
  background-color: #5C07A3;
  color: #ffffff;
  border: none;
  width: 100%;
  height: 50px;
  border-radius: 5px;
  font-weight: 600;
  margin-bottom: 24px;
}
</style>
