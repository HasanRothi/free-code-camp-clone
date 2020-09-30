<template>
  <div>
    <v-app class="container pa-8">
      <v-main
        style="font-family: Georgia, serif; text-align: center"
        class="pa-10"
      >
        welcome
        <div class="pa-8">
          <v-btn class="white black-text">View my Portfolio</v-btn>

          <v-btn>Update my account</v-btn>
          <v-btn>Go to current challange</v-btn>
        </div>
        <div class="pa-2">
          <h2><i>"Never memorize something that can look up."</i></h2>
          <i>-Albert Einstein</i>
        </div>
      </v-main>
      <v-row justify="center" style="font-family: cursive">
        <v-expansion-panels inset>
          <v-expansion-panel v-for="(course, i) in courseList" :key="i">
            <v-expansion-panel-header
              >{{ course.title }} --
              <b>{{ course.subTitle.length }}</b></v-expansion-panel-header
            >
            <v-expansion-panel-content>
              <!-- {{ course.subTitle }} -->
              <!-- sub title -->
              <v-row justify="center">
                <v-expansion-panels>
                  <v-expansion-panel
                    v-for="(subTitle, j) in course.subTitle"
                    :key="j"
                  >
                    <v-expansion-panel-header
                      >{{ subTitle[0].topicTitle }} --
                      <b>
                        {{ subTitle[1].topics.length }}
                      </b></v-expansion-panel-header
                    >
                    <v-expansion-panel-content>
                      <!-- topic here -->
                      <v-expansion-panels>
                        <v-expansion-panel
                          v-for="(topic, l) in subTitle[1].topics"
                          :key="l"
                        >
                          <v-btn block @click="editorRoute(topic)">{{
                            topic
                          }}</v-btn>
                        </v-expansion-panel>
                      </v-expansion-panels>
                    </v-expansion-panel-content>
                  </v-expansion-panel>
                </v-expansion-panels>
              </v-row>
              <!-- sub title end -->
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
      </v-row>
    </v-app>
    <footerComp />
  </div>
</template>

<script>
import footerComp from "../components/footer";
export default {
  layout: "",
  head() {
    return {
      title: "Learn to code at Home",
    };
  },
  data() {
    return {
      courseList: this.$store.state.courseList.courseList,
    };
  },
  created() {
    // console.log(this.courseList);
  },
  components: {
    footerComp,
  },

  methods: {
    editorRoute(topic) {
      this.$router.push({ path: `/editor/${topic}` });
    },
  },
};
</script>
