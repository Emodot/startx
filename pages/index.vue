<template>
  <div class="container">
    <p class="page-title">
      DASHBOARD
    </p>
    <hr class="grey-line">
    <div class="inner">
      <div class="lhs">
        <div class="cards">
          <div v-for="(card, index) in cards" :key="index" class="card">
            <div class="card-top">
              <p class="card-name">
                {{ card.name }}
              </p>
            </div>
            <div class="card-num">
              {{ card.number ? currency(card.number) : card.plan }}
            </div>
          </div>
        </div>
        <div class="dashboard-table">
          <TablesDashboardTable />
        </div>
      </div>
      <div class="rhs">
        <div class="new-magazine">
          <p class="new-title">
            Upload CV <span class="new">(New)</span>
          </p>
          <hr>
          <div class="upload-img">
            <img src="~assets/img/upload-cv.png" alt="">
          </div>
          <p class="click">
            Click the button to upload your CV
          </p>
          <p class="pdf-only">
            (.pdf document only)
          </p>
          <div class="upload-btn">
            <button @click="newMagazine = true">
              Upload
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import functions from '@/utils/functions'
export default {
  layout: 'MainLayout',
  data () {
    return {
      currency: functions.formatCurrency,
      cards: [
        {
          name: 'Total Data Uploads',
          number: '564'
        },
        {
          name: 'Total Amount Subscribed',
          number: '25,791'
        },
        {
          name: 'Subscription Plan',
          plan: 'Monthly'
        }
      ]
    }
  }
}
</script>

<style scoped>
.container {
  padding: 50px 5rem;
}

.inner {
  display: flex;
}

.lhs {
  flex-basis: 70%;
  margin-right: 2%;
}

.rhs {
  flex-basis: 30%;
}

.cards {
  margin-bottom: 40px;
  display: flex;
}

.card {
  background-color: white;
  flex-basis: 23%;
  margin-right: 2%;
  padding: 20px;
}

.card-top {
  display: flex;
  justify-content: space-between;
  margin-bottom: 15px;
}

.card-num {
  margin-top: 30px;
  font-size: 24px;
  font-weight: 500;
}

.dashboard-table {
  width: 100%;
}

/* RHS  */

.new-magazine {
  background-color: white;
  padding: 30px 40px;
}

.new-title {
  font-size: 14px;
  font-weight: 500;
}

.new {
  color: #008A27;
  font-style: italic;
}

hr {
  border: none;
  border-top: 1px solid #E7E8F2;
  margin: 20px 0;
}

.upload-img {
  text-align: center;
}

.click {
  font-weight: 500;
  text-align: center;
  margin: 12px 0;
}

.pdf-only {
  color: #4D4D4D;
  font-weight: 300;
  text-align: center;
}

.upload-btn {
  text-align: center;
}

.upload-btn button {
  cursor: pointer;
  width: 169px;
  height: 40px;
  margin-top: 30px;
  background: #5C07A3;
  border-radius: 3px;
  color: white;
  border: none;
  font-size:11px;
}

@media screen and (max-width: 600px) {
  .container {
    padding: 20px;
  }

  .inner {
    flex-direction: column;
  }

  .cards {
    flex-direction: column;
  }

  .card {
    margin-top: 20px;
  }

  .card-num {
    font-size: 22px;
  }

  .card-name {
    font-size: 15px;
  }

  .table-top {
    padding: 0 10px;
  }

  .rhs {
    margin-top: 3rem;
  }
}
</style>
