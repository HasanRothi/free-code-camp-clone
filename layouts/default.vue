<template>
  <div>
    <v-app>
      <v-app-bar app dense fixed dark>
        <v-toolbar-item>
          <!-- <v-text-field
            hide-details
            prepend-icon="mdi-magnify"
            single-line
            placeholder="Search 6,000+ tutorials"
          ></v-text-field> -->
          <v-autocomplete
            prepend-icon="mdi-magnify"
            v-model="select"
            :loading="loading"
            :items="items"
            :search-input.sync="search"
            cache-items
            class="mx-4"
            flat
            hide-no-data
            hide-details
            label="Search 6,000+ tutorials"
            solo-inverted
          ></v-autocomplete>
        </v-toolbar-item>
        <v-spacer></v-spacer>

        <v-toolbar-title class="d-none d-md-block d-lg-block">
          <NuxtLink id="link" to="/"
            >freeCodeCampClone</NuxtLink
          ></v-toolbar-title
        >
        <v-spacer></v-spacer>

        <v-toolbar-items
          style="padding: 1%"
          class="d-none d-md-block d-lg-block"
          ><NuxtLink id="link" to="/news"> /news</NuxtLink></v-toolbar-items
        >

        <v-toolbar-items
          style="padding: 1%"
          class="d-none d-md-block d-lg-block"
        >
          <NuxtLink id="link" to="/learn"> /learn</NuxtLink></v-toolbar-items
        >

        <v-toolbar-items
          style="padding: 1%"
          class="d-none d-md-block d-lg-block"
        >
          <NuxtLink id="link" to="/forum"> /forum</NuxtLink></v-toolbar-items
        >
        <v-app-bar-nav-icon @click="drawar = !drawar"></v-app-bar-nav-icon>
      </v-app-bar>
      <v-navigation-drawer v-model="drawar" absolute temporary>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title class="title"> Free Code Camp</v-list-item-title>
            <v-list-item-subtitle> <i>Learn to code</i> </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-divider></v-divider>
        <div class="pa-2">
          <v-btn block to="/news">News</v-btn>
          <v-divider></v-divider>
          <v-btn block to="/learn">Learn</v-btn>
          <v-divider></v-divider>
          <v-btn block to="/forum">Forum</v-btn>
        </div>
      </v-navigation-drawer>
      <nuxt />
    </v-app>
  </div>
</template>

<script>
export default {
  data() {
    return {
      drawar: false,
      loading: false,
      items: [],
      search: null,
      select: null,
      states: [],
    };
  },
  watch: {
    search(val) {
      val && val !== this.select && this.querySelections(val);
      // console.log(val);
    },
  },
  methods: {
    querySelections(v) {
      this.loading = true;
      // Simulated ajax query
      setTimeout(() => {
        this.items = this.states.filter((e) => {
          return (e || "").toLowerCase().indexOf((v || "").toLowerCase()) > -1;
        });

        this.loading = false;
      }, 500);
    },
  },
  created() {
    this.$store.state.courseList.courseList.forEach((u) => {
      // console.log(u.subTitle.length);
      u.subTitle.forEach((v, j) => {
        // console.log(v[0].topicTitle);
        v[1].topics.forEach((c) => {
          // console.log(c);
          this.states.push(c);
        });
      });
    });
    console.log(this.states);
  },
};
</script>
<style lang="scss" scoped>
#link {
  text-decoration: none;
  color: inherit;
}
#link:hover {
  color: cornflowerblue;
}
</style>