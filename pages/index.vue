<template>
  <div>
    <v-app class="container">
      <v-main style="font-family: cursive" class="pa-10">
        <h1 class="pa-2">Learn to code at home.</h1>
        <h1 class="pa-2">Build projects.</h1>
        <h1 class="pa-2">Earn certifications.</h1>
        <h4 class="pa-2">
          Since 2014, more than 40,000 freeCodeCamp.org graduates have gotten
          jobs at tech companies including:
        </h4>
        <v-row>
          <v-col v-for="logo in companyLogo" :key="logo.name">
            <img :src="logo" height="50%" width="50%" />
          </v-col>
        </v-row>
        <getStartedBtn title="Get Started (it's free)" />
        <div
          class="d-none d-md-block d-lg-block pa-10"
          style="text-align: center"
        >
          <img src="../assets/images/frontImage.png" />
          <span
            >freeCodeCamp students at a local study group in South Korea.</span
          >
        </div>
      </v-main>
      <asSeenin />
      <alumniSay />

      <courseList />
      <getStartedBtn title="Get Started (it's free)" />
      <v-btn
        v-scroll="onScroll"
        v-show="fab"
        fab
        dark
        fixed
        bottom
        right
        color="secondary"
        @click="toTop"
      >
        <v-icon>keyboard_arrow_up</v-icon>
      </v-btn>
    </v-app>
    <footerComp class="pa-4" />
  </div>
</template>

<script>
import asSeenin from "../components/asSeenIn";
import alumniSay from "../components/alumniSay";
import courseList from "../components/courseList";
import getStartedBtn from "../components/getStartedBtn";
import footerComp from "../components/footer";
export default {
  layout: "",
  head() {
    return {
      title: "Learn to code",
    };
  },
  scrollToTop: true,
  components: {
    asSeenin: asSeenin,
    alumniSay: alumniSay,
    courseList,
    getStartedBtn,
    footerComp,
  },
  data() {
    return {
      companyLogo: [
        "https://upload.wikimedia.org/wikipedia/commons/f/fa/Apple_logo_black.svg",
        "https://upload.wikimedia.org/wikipedia/commons/2/20/Google-Logo.svg",
        "https://upload.wikimedia.org/wikipedia/en/5/5d/Microsoft_%28logo%29.svg",
        "https://upload.wikimedia.org/wikipedia/commons/a/a9/Amazon_logo.svg",
        "https://upload.wikimedia.org/wikipedia/commons/2/26/Spotify_logo_with_text.svg",
      ],
      fab: false,
    };
  },
  methods: {
    onScroll(e) {
      if (typeof window === "undefined") return;
      const top = window.pageYOffset || e.target.scrollTop || 0;
      this.fab = top > 20;
    },
    toTop() {
      this.$vuetify.goTo(0);
    },
  },
};
</script>
