<template>
  <div class="container">
    <div class="back" @click="window.history.back()">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path opacity="0.4" d="M12 22.0002C6.485 22.0002 2 17.5142 2 12.0002C2 6.48621 6.485 2.00021 12 2.00021C17.514 2.00021 22 6.48621 22 12.0002C22 17.5142 17.514 22.0002 12 22.0002" fill="#75759E" />
        <path d="M13.4425 16.2209C13.2515 16.2209 13.0595 16.1479 12.9135 16.0019L9.42652 12.5319C9.28552 12.3909 9.20652 12.1999 9.20652 11.9999C9.20652 11.8009 9.28552 11.6099 9.42652 11.4689L12.9135 7.99692C13.2065 7.70492 13.6805 7.70492 13.9735 7.99892C14.2655 8.29292 14.2645 8.76792 13.9715 9.05992L11.0185 11.9999L13.9715 14.9399C14.2645 15.2319 14.2655 15.7059 13.9735 15.9999C13.8275 16.1479 13.6345 16.2209 13.4425 16.2209" fill="#75759E" />
      </svg>
      <p>Back</p>
    </div>
    <div class="inner">
      <p class="head">
        Edit Profile Data
      </p>
      <div class="inner-tab">
        <div
          :class="activeTab.includes('personal') ? 'active' : 'inactive'"
          class="tab"
          @click="activeTab = 'personal'"
        >
          Personal Information
        </div>
        <div
          :class="activeTab.includes('business') ? 'active' : 'inactive'"
          class="tab"
          @click="activeTab = 'business'"
        >
          Business Information
        </div>
        <div
          :class="activeTab.includes('other') ? 'active' : 'inactive'"
          class="tab"
          @click="activeTab = 'other'"
        >
          Other Information
        </div>
      </div>
      <div v-if="activeTab == 'personal'" class="tab-1">
        <FormsPersonalInfo />
      </div>
      <div v-if="activeTab == 'business'" class="tab-1">
        <FormsBusinessInfo />
      </div>
      <div v-if="activeTab == 'other'" class="tab-1">
        <FormsOtherInfo />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'MainLayout',
  data () {
    return {
      activeTab: 'personal'
    }
  }
}
</script>

<style scoped>
.container {
  padding: 50px 5rem;
}

.back {
  display: flex;
  align-items: center;
}

.back p {
  margin-left: 10px;
  color: #75759E;
}

.inner {
  margin-top: 4rem;
  width: 80%;
  background-color: #fff;
  border-radius: 20px;
  padding: 30px 40px;
}

.head {
  font-weight: 500;
}

.inner .active {
  color: #5C07A3 !important;
  border-bottom: 3px solid #5C07A3;
}

.inner-tab {
  display: flex;
  margin-top: 50px;
  border-bottom: 1px solid #75759e6e;
}

.inner .tab{
  padding: 15px;
  cursor: pointer;
  margin-right: 70px;
  color: #777777;
}

.tab-1 {
  padding-top: 3rem;
}
</style>
