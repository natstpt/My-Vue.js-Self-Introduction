<template>
  <section id="about" class="hide-overflow">
    <v-layout white>
      <v-flex xs12 md6 pa-5>
        <base-bubble-1 style="transform: translate(5%, -5%)" />
        <base-heading class="info--text">About Me</base-heading>
        <base-text class="mb-5">
          I'm Natkamon Sunthonphithak
          <br />Software Trainee @Inet Khonkaen
        </base-text>

        <base-heading class="info--text">Hobby</base-heading>
        <v-layout row justify-center>
          <v-btn color="primary" dark @click.stop="dialog = true">Click Me!</v-btn>

          <v-dialog v-model="dialog" max-width="853">
            <v-card>
              <v-card-title class="headline">Thai Chess (Makrukthai)</v-card-title>

              <iframe src="http://127.0.0.1:5000" height="600" width="700"></iframe>

              <v-card-actions>
                <v-spacer></v-spacer>

                <v-btn color="green darken-1" flat="flat" @click="dialog = false">Close</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-layout>

        <base-heading class="info--text">
          <br />Skills
        </base-heading>
        <v-alert outlined color="info">
          <v-layout v-for="(skill, i) in skills" :key="i" style="color: #69A1BB;" wrap>
            <v-flex xs6 text-uppercase v-text="skill.name" />
            <v-flex xs6 text-xs-right v-text="`${skill.value}%`" />
            <v-progress-linear :value="skill.value" color="info" height="8" />
          </v-layout>
        </v-alert>
      </v-flex>
      <v-flex hidden-sm-and-down md6>
        <v-img :src="require('@/assets/aboutme.png')" height="100%" />
      </v-flex>
    </v-layout>

    <v-layout>
      <v-carousel>
        <v-carousel-item v-for="(item,i) in items" :key="i" :src="item.src"></v-carousel-item>
      </v-carousel>
    </v-layout>
  </section>
</template>

<script>
export default {
  data: () => ({
    dialog: false,
    skills: [
      {
        name: "Vue.js Frontend",
        value: 10
      },
      {
        name: "Node js Backend",
        value: 30
      },
      {
        name: "Thai Chess (Makrukthai)",
        value: 100
      }
    ],
    items: [
      {
        src: "https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg"
      },
      {
        src: "https://cdn.vuetifyjs.com/images/carousel/sky.jpg"
      },
      {
        src: "https://cdn.vuetifyjs.com/images/carousel/bird.jpg"
      },
      {
        src: "https://cdn.vuetifyjs.com/images/carousel/planet.jpg"
      }
    ]
  })
};
</script>
