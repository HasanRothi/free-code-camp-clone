<template>
  <div
    red
    class="pa-6"
    style="font-family: Times New Roman; background-color: #dfdfe2"
  >
    <v-row>
      <v-col sm="12" md="6">
        <p>
          freeCodeCamp is a donor-supported tax-exempt 501(c)(3) nonprofit
          organization (United States Federal Tax Identification Number:
          82-0779546)
        </p>
        <p>
          Our mission: to help people learn to code for free. We accomplish this
          by creating thousands of videos, articles, and interactive coding
          lessons - all freely available to the public. We also have thousands
          of freeCodeCamp study groups around the world.
        </p>
        <p>
          Donations to freeCodeCamp go toward our education initiatives, and
          help pay for servers, services, and staff.
        </p>
        <h4>
          You can <u to="/donate">make a tax-deductible donation here.</u>
        </h4>
      </v-col>
      <v-col sm="12" md="6">
        <h3 style="text-align: center">Trending Guides</h3>
        <v-row v-for="(trends, i) in trendingGuids" :key="i">
          <v-col sm="12" md="4">
            <span>{{ trends }}</span>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <v-divider></v-divider>
    <div style="display: flex">
      <div v-for="(item, i) in footerItem" :key="i" class="pa-1">
        <i>
          <nuxt-link to="/itemsDetails"> {{ item }}</nuxt-link></i
        >
      </div>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      trendingGuids: [
        "javascript",
        "Javascript Promise",
        "What is a Proxy Server",
        "Css Box Shadow",
        "What is Github?",
        "Cat Command in Linux",
      ],
      footerItem: [
        "About",
        "Alumni Network",
        "Open Source",
        "Shop",
        "Support",
        "Sponsors",
        "Academic Honesty",
        "Code of Conduct",
        "Privacy Policy",
        "Terms Of Service",
        "Copyright Policy",
      ],
    };
  },
};
</script>