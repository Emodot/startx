<template>
  <div>
    <div v-if="transLoading" class="table-loader">
      <TableLoader />
    </div>
    <div v-else class="table-container">
      <div class="table-top">
        <p class="table-title">
          Latest Subscription
        </p>
        <!-- <p class="view-all" @click="$router.push('/subscriptions')">
          View All
        </p> -->
      </div>
      <table>
        <tr class="table-header">
          <th class="id">
            ID
          </th>
          <th class="domain">
            Domain
          </th>
          <th class="amount">
            Sitename
          </th>
          <th class="date">
            Date
          </th>
          <th class="amount">
            Channel
          </th>
          <th class="amount">
            Status
          </th>
        </tr>
        <tr v-for="(transaction, index) in transactions" :key="index" class="table-details">
          <td class="id">
            {{ transaction.id }}
          </td>
          <td class="domain">
            {{ transaction.domain }}
          </td>
          <td class="amount">
            {{ transaction.sitename }}
          </td>
          <td class="date">
            {{ transaction.date }}
          </td>
          <td class="amount">
            {{ transaction.channel }}
          </td>
          <td class="type-details" :class="transaction.status === 'Success' ? 'success' : '' ">
            {{ transaction.status }}
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
// import Cookies from 'js-cookie'
export default {
  data () {
    return {
      transLoading: false,
      transactions: [
        {
          id: '#ND1283',
          domain: 'google.com',
          sitename: 'Google',
          date: '22, JAN. 2021',
          channel: 'API',
          status: 'Success'
        },
        {
          id: '#ND1283',
          domain: 'google.com',
          sitename: 'Google',
          date: '22, JAN. 2021',
          channel: 'API',
          status: 'Failed'
        },
        {
          id: '#ND1283',
          domain: 'google.com',
          sitename: 'Google',
          date: '22, JAN. 2021',
          channel: 'API',
          status: 'Failed'
        },
        {
          id: '#ND1283',
          domain: 'google.com',
          sitename: 'Google',
          date: '22, JAN. 2021',
          channel: 'API',
          status: 'Success'
        },
        {
          id: '#ND1283',
          domain: 'google.com',
          sitename: 'Google',
          date: '22, JAN. 2021',
          channel: 'API',
          status: 'Success'
        },
        {
          id: '#ND1283',
          domain: 'google.com',
          sitename: 'Google',
          date: '22, JAN. 2021',
          channel: 'API',
          status: 'Failed'
        },
        {
          id: '#ND1283',
          domain: 'google.com',
          sitename: 'Google',
          date: '22, JAN. 2021',
          channel: 'API',
          status: 'Success'
        }
      ]
    }
  },
  created () {
    // this.getTransactions()
    // this.getPaymentHistory()
  },
  methods: {
    // getTransactions () {
    //   this.transLoading = true
    //   this.$axios.$get('/get_transaction_by_id/', {
    //     headers: {
    //       Authorization: `Bearer ${Cookies.get('token')}`
    //     }
    //   }).then((response) => {
    //     // console.log(response)
    //     this.transLoading = false
    //     this.transactions = response.data
    //   })
    // },
    // getPaymentHistory () {
    //   // this.transLoading = true
    //   this.$axios.$get('/payment_history/', {
    //     headers: {
    //       Authorization: `Bearer ${Cookies.get('token')}`
    //     }
    //   }).then((response) => {
    //     // console.log(response)
    //     // this.transLoading = false
    //     // this.transactions = response.data
    //   })
    // }
  }
}
</script>

<style scoped>

.table-top {
  display: flex;
  justify-content: space-between;
  padding: 30px 30px;
}

.table-title {
  font-size: 15px;
  font-weight: 500;
  color: #000000;
}

.view-all {
  font-size: 15px;
  cursor: pointer;
}
.table-loader {
  margin-top: 100px;
}
.table-container {
  background-color: #ffffff;
  border-radius: 10px;
  width: 100%;
  /* border: 1px solid #1A2440; */
}
table, th, td {
  /* border: 1px solid #fff; */
  border-collapse: collapse;
  font-size: 15px;
}
.table-header {
  height: 60px;
  background-color: #F0F2F4;
  padding: 0 20px;
}

.table-header th {
  font-weight: 500;
  color: #000000;
}
.table-details {
  height: 60px;
  padding: 0 20px;
}
.table-details:nth-child(odd) {
  height: 60px;
  background-color: #F9FAFB;
  padding: 0 20px;
}
th {
  text-align: left;
}

.id {
  width: 13rem;
  padding-left: 25px;
}

.domain {
  width: 14rem;
}

.date {
  width: 18rem;
}

.description {
  width: 20rem;
}

.type {
  width: 10rem;
}

.type-details {
  width: 10rem;
  color: #EE3E3E;
}

.success {
  color: #4ABF21;
}

.amount {
  width: 13rem;
}

@media only screen and (max-width: 500px) {
  .table-container {
    width: 100%;
    overflow: auto;
  }

  table {
    width: 47rem;
  }

  .date {
    width: 25rem;
  }
}
</style>
