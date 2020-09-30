<template>
  <div class="container">
    <h1 style="text-align: center">Earn free verified certifications in:</h1>
    <div v-for="course in courseList" :key="course.name" class="pa-1">
      <span display="flex">
        <v-btn block to="/learn"
          >{{ course.title }}
          <v-icon class="ml-3 grey black--text">double_arrow</v-icon></v-btn
        >
      </span>
    </div>

    <v-card> </v-card>
  </div>
</template>


<script>
export default {
  data() {
    return {
      courseList: this.$store.state.courseList.courseList,
    };
  },
};
</script>
