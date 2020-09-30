<template>
  <div>
    <v-app>
      <v-main> {{ topic }} </v-main>
    </v-app>
  </div>
</template>

<script>
export default {
  layout: "",
  head() {
    return {
      title: `Editor | ${this.topic}`,
    };
  },
  data() {
    return {
      topic: this.$route.params.topic,
    };
  },
  created() {
    console.log("Editor");
  },

  methods: {},
};
</script>
