<template>
  <v-card>
    <v-toolbar color="purple" flat>
      <v-text-field
        append-icon="mdi-microphone"
        class="mx-4"
        label="Search"
        prepend-inner-icon="mdi-magnify"
        variant="solo-inverted"
        flat
        hide-details
      ></v-text-field>

      <template v-slot:extension>
        <v-tabs
          v-model="tabs"
          align-tabs="center"
        >
          <v-tab
            v-for="n in 3"
            :key="n"
            :text="`Item ${n}`"
          ></v-tab>
        </v-tabs>
      </template>
    </v-toolbar>

    <v-tabs-window v-model="tabs">
      <v-tabs-window-item>
        <v-card flat>
          <v-card-text>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
          </v-card-text>
        </v-card>
      </v-tabs-window-item>
      <v-tabs-window-item>
        <v-card flat>
          <v-card-title class="text-h5">
            An awesome title
          </v-card-title>
          <v-card-text>
            <p>
              Duis lobortis massa imperdiet quam. Donec vitae orci sed dolor rutrum auctor. Vestibulum facilisis, purus nec pulvinar iaculis, ligula mi congue nunc, vitae euismod ligula urna in dolor. Praesent congue erat at massa.
            </p>

            <p>
              Aenean posuere, tortor sed cursus feugiat, nunc augue blandit nunc, eu sollicitudin urna dolor sagittis lacus. Pellentesque egestas, neque sit amet convallis pulvinar, justo nulla eleifend augue, ac auctor orci leo non est. Etiam sit amet orci eget eros faucibus tincidunt. Donec sodales sagittis magna.
            </p>

            <p class="mb-0">
              Ut leo. Suspendisse potenti. Duis vel nibh at velit scelerisque suscipit. Fusce pharetra convallis urna.
            </p>
          </v-card-text>
        </v-card>
      </v-tabs-window-item>
      <v-tabs-window-item>
        <v-card flat>
          <v-card-title class="text-h5">
            An even better title
          </v-card-title>
          <v-card-text>
            <p>
              Maecenas ullamcorper, dui et placerat feugiat, eros pede varius nisi, condimentum viverra felis nunc et lorem. Sed hendrerit. Maecenas malesuada. Vestibulum ullamcorper mauris at ligula. Proin faucibus arcu quis ante.
            </p>

            <p class="mb-0">
              Etiam vitae tortor. Curabitur ullamcorper ultricies nisi. Sed magna purus, fermentum eu, tincidunt eu, varius ut, felis. Aliquam lobortis. Suspendisse potenti.
            </p>
          </v-card-text>
        </v-card>
      </v-tabs-window-item>
    </v-tabs-window>
  </v-card>
</template>

<script setup>
  import { ref } from 'vue'

  const tabs = ref(null)
</script>

<script>
  export default {
    data () {
      return {
        tabs: null,
      }
    },
  }
</script>
