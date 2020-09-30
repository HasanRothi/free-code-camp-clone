<template>
  <div
    class="white--text pa-10"
    style="text-align: center; background-color: #3b3b4f"
  >
    <h2>As Seen In :</h2>
    <v-row>
      <v-col v-for="logo in icons" :key="logo.name">
        <img :src="logo" height="50%" width="50%" />
      </v-col>
    </v-row>
  </div>
</template>


<script>
export default {
  data() {
    return {
      icons: [
        "https://upload.wikimedia.org/wikipedia/commons/e/eb/BBC.svg",
        "https://upload.wikimedia.org/wikipedia/commons/b/b3/Time_Magazine_logo.svg",
        "https://upload.wikimedia.org/wikipedia/commons/7/77/The_New_York_Times_logo.png",
        "https://upload.wikimedia.org/wikipedia/commons/1/14/Inc.svg",
      ],
    };
  },
};
</script>
