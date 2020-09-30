<template>
  <div>
    <h1 class="pa-6" style="text-align: center">
      Here is what our alumni say about freeCodeCamp:
    </h1>
    <div v-for="alumni in alumniInfo" :key="alumni.name" class="pa-4">
      <v-card>
        <v-row>
          <v-col
            xs="12"
            sm="12"
            md="4"
            lg="4"
            xl="4"
            style="text-align: center"
          >
            <img width="250px" height="250px" :src="alumni.img" />
          </v-col>
          <v-col xs="12" sm="12" md="8" lg="8" xl="8">
            <v-card-title>{{ alumni.name }} in {{ alumni.place }}</v-card-title>

            <v-card-title>
              {{ alumni.position }} at {{ alumni.company }}</v-card-title
            >
            <v-card-text>{{ alumni.speech }}</v-card-text>
          </v-col>
        </v-row>
      </v-card>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      alumniInfo: this.$store.state.alumniSay.alumniInfo,
    };
  },
};
</script>
