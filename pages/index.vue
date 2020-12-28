<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card>
        <v-card-title class="headline">
          Welcome, my name is Daniel Melton
        </v-card-title>
        <v-card-text>
          <p>
            I am a graduaute with a Bachelors of Science, in software
            engineering. Before attending a university, I was working freelance
            as a webmaster on mutilpe wordpress sites. The experience I gained
            made me more eager to learn different aspects of programming. With
            the knowledge I have gained over the past few years between school
            and working, I am postive that I have what it takes to help your
            company to achieve and exceed its goals.
          </p>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-title> Skills </v-card-title>
        <v-card-text>
          <div v-for="(skill, y) in skills" :key="y">
            <p>{{ skill.text }}</p>
            <v-progress-linear
              :value="skill.value"
              :color="skill.color"
              :height="skill.height"
            ></v-progress-linear>
            <br />
          </div>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>


<script>
export default {
  data() {
    return {
      skills: [
        {
          text: "Html/Css",
          value: 92,
          color: "amber",
          height: 10,
        },
        {
          text: "Javascript",
          value: 75,
          color: "amber",
          height: 10,
        },
        {
          text: "Python",
          value: 81,
          color: "amber",
          height: 10,
        },
        {
          text: "C/C++/Go",
          value: 71,
          color: "amber",
          height: 10,
        },
        {
          text: "Databases",
          value: 79,
          color: "amber",
          height: 10,
        },
      ],
    };
  },
};
</script>
