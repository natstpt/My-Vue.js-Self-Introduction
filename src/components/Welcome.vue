<template>
  <section id="welcome" class="hide-overflow">
    <v-layout>
      <v-flex hidden-sm-and-down md6>
        <v-img :src="require('@/assets/welcome.png')" height="100vh" />
      </v-flex>

      <v-flex
        xs12
        md6
        align-content-space-between
        layout
        :pa-5="$vuetify.breakpoint.smAndDown"
        wrap
      >
        <base-bubble-1 style="transform: rotate(180deg) translateY(25%)" />

        <v-layout align-center justify-center>
          <v-flex xs10 md6>
            <base-heading>Profile</base-heading>

            <v-timeline>
              <template v-slot:opposite>
                <span>Bachelor Degrees</span>
              </template>
              <v-card class="elevation-2">
                <v-card-title class="headline">Khon Kaen University</v-card-title>
              </v-card>
            </v-timeline>
            <v-timeline>
              <template v-slot:opposite>
                <span>Working</span>
              </template>
              <v-card class="elevation-2">
                <v-card-title class="headline">INET Khon Kaen</v-card-title>
              </v-card>
            </v-timeline>
            <v-timeline>
              <template v-slot:opposite></template>
            </v-timeline>

            <v-layout row justify-center>
              <v-btn color="primary" dark @click.stop="dialog = true"></v-btn>
              <v-dialog v-model="dialog" max-width="853">
                <v-card>
                  <v-card-title class="headline">Hello</v-card-title>

                  <iframe
                    src="http://www.youtube.com/embed/2pmgu6Yfbb8?autoplay=1"
                    width="960"
                    height="447"
                    frameborder="0"
                    allowfullscreen
                  ></iframe>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn color="green darken-1" flat="flat" @click="dialog = false">Close</v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
            </v-layout>
          </v-flex>
        </v-layout>

        <base-bubble-2 style="transform: rotate(180deg) translate(-200px, -15%)" />
      </v-flex>
    </v-layout>
  </section>
</template>

<script>
export default {
  data() {
    return {
      dialog: false
    };
  }
};
</script>