<template>
  <v-row>
    <v-col v-for="(website, len) in websites" :key="len">
      <v-card class="mx-auto" max-width="400">
        <v-img height="220" :src="website.img"></v-img>
        <v-card-title> {{ website.title }} </v-card-title>
        <v-card-text>
          {{ website.text }}
        </v-card-text>
        <v-card-actions>
          <v-btn
            v-if="website.url !== ''"
            color="amber lighten-2"
            :href="website.url"
            :target="website.target"
            text
          >
            Visit Website
          </v-btn>
          <v-spacer></v-spacer>
          <v-btn
            v-if="website.github !== ''"
            color="amber lighten-2"
            :href="website.github"
            :target="website.target"
            text
          >
            View Code
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      websites: [
        {
          img: "/moneybalancer.png",
          title: "Money Balancer",
          text:
            "Accounting application built for application domain course. Using the knowledge of\
          accounting to produce an application that will allow for the user to do basic accounting\
          activities such as journaling, creating accounts, and viewing/generating reports",
          url: "http://moneybalancer.pythonanywhere.com/",
          github: "https://github.com/DanMelt205/MB",
          target: "_blank",
        },
        {
          img: "converter.png",
          title: "Basic Converter",
          text:
            "Project was hosted on AWS Ec2 using Flask for the backend api and React js frontend.\
             The project allows for the user to convert the basic measurements tempature, weight,\
              and speed. Then the user can view the last 5 entries provided from the database.",
          url: "",
          github: "https://github.com/DanMelt205/cloud_project",
          target: "_blank",
        },
      ],
    };
  },
};
</script>