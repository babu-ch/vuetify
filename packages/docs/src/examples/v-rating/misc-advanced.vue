<template>
  <v-card
    class="mx-auto overflow-hidden"
    max-width="600"
  >
    <v-row>
      <v-col
        class="d-flex"
        cols="6"
      >
        <v-img src="https://cdn.vuetifyjs.com/images/ratings/fortnite1.png"></v-img>
      </v-col>

      <v-col cols="6">
        <v-container class="pa-0 ps-2 my-n1">
          <v-row>
            <v-col
              class="d-flex"
              cols="7"
            >
              <v-img src="https://cdn.vuetifyjs.com/images/ratings/fortnite2.png"></v-img>
            </v-col>

            <v-col
              class="d-flex"
              cols="5"
            >
              <v-img src="https://cdn.vuetifyjs.com/images/ratings/fortnite3.png"></v-img>
            </v-col>

            <v-col
              class="d-flex"
              cols="5"
            >
              <v-img src="https://cdn.vuetifyjs.com/images/ratings/fortnite4.png"></v-img>
            </v-col>

            <v-col
              class="d-flex"
              cols="7"
            >
              <v-img src="https://cdn.vuetifyjs.com/images/ratings/fortnite5.png"></v-img>
            </v-col>
          </v-row>
        </v-container>
      </v-col>
    </v-row>

    <v-card-title class="align-start">
      <div>
        <span class="text-h5">FORTNITE</span>
        <div class="text-grey font-weight-light">
          Video game
        </div>
      </div>

      <v-spacer></v-spacer>

      <v-dialog
        v-model="dialog"
        width="400"
      >
        <template v-slot:activator="{ props }">
          <v-icon v-bind="props" icon="mdi-share-variant"></v-icon>
        </template>

        <v-card>
          <v-card-title class="d-flex">
            <span class="text-h6 font-weight-bold">Share</span>
            <v-spacer></v-spacer>

            <v-btn class="mx-0" icon @click="dialog = false">
              <v-icon>mdi-close-circle-outline</v-icon>
            </v-btn>
          </v-card-title>

          <v-list>
            <v-list-item prepend-icon="mdi-facebook" title="Facebook"></v-list-item>
            <v-list-item prepend-icon="mdi-twitter" title="Twitter"></v-list-item>
            <v-list-item prepend-icon="mdi-email" title="Email"></v-list-item>
          </v-list>

          <v-text-field
            ref="link"
            :label="copied ? 'Link copied' : 'Click to copy link'"
            class="pa-4"
            model-value="https://g.co/kgs/nkrK43"
            readonly
            @click="copy"
          ></v-text-field>
        </v-card>
      </v-dialog>
    </v-card-title>

    <v-divider></v-divider>

    <v-card-actions>
      <span class="ps-2 text-grey-darken-2 font-weight-light text-caption">16,544 reviews</span>

      <v-spacer></v-spacer>

      <v-rating
        v-model="rating"
        length="10"
        readonly
      >
        <template v-slot:item="props">
          <v-icon
            :color="props.isFilled ? 'purple-darken-4' : ''"
            :icon="`mdi-numeric-${props.index}-box`"
            size="large"
          ></v-icon>
        </template>
      </v-rating>
    </v-card-actions>
    <div class="pa-4 pt-0 text-caption">
      <em>Portions of the materials used are trademarks and/or copyrighted works of Epic Games, Inc. All rights reserved by Epic. This material is not official and is not endorsed by Epic.</em>
    </div>
  </v-card>
</template>

<script setup>
  import { ref } from 'vue'

  const link = ref()

  const copied = ref(false)
  const dialog = ref(false)
  const rating = ref(10)

  function copy () {
    link.value.focus()
    document.execCommand('selectAll', false, null)
    copied.value = document.execCommand('copy')
  }
</script>

<script>
  export default {
    data: () => ({
      copied: false,
      dialog: false,
      rating: 10,
    }),

    methods: {
      copy () {
        this.$refs.link.focus()

        document.execCommand('selectAll', false, null)

        this.copied = document.execCommand('copy')
      },
    },
  }
</script>
