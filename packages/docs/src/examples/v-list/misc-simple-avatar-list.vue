<template>
  <v-card
    class="mx-auto"
    max-width="500"
  >
    <v-toolbar
      color="indigo"
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Inbox</v-toolbar-title>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-toolbar>
    <v-list>
      <v-list-item
        v-for="item in items"
        :key="item.title"
      >
        <template v-slot:prepend>
          <v-avatar>
            <v-icon
              v-if="item.icon"
              color="pink"
            >
              mdi-star
            </v-icon>
          </v-avatar>
        </template>

        <v-list-item-title>{{ item.title }}</v-list-item-title>

        <template v-slot:append>
          <v-avatar>
            <v-img :src="item.avatar"></v-img>
          </v-avatar>
        </template>
      </v-list-item>
    </v-list>
  </v-card>
</template>

<script setup>
  const items = [
    { icon: true, title: 'Jason Oner', avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg' },
    { title: 'Travis Howard', avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg' },
    { title: 'Ali Connors', avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg' },
    { title: 'Cindy Baker', avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg' },
  ]
</script>

<script>
  export default {
    data () {
      return {
        items: [
          { icon: true, title: 'Jason Oner', avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg' },
          { title: 'Travis Howard', avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg' },
          { title: 'Ali Connors', avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg' },
          { title: 'Cindy Baker', avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg' },
        ],
      }
    },
  }
</script>
