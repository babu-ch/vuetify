<template>
  <v-card
    class="mx-auto"
    max-width="500"
  >
    <v-toolbar
      color="teal"
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Topics</v-toolbar-title>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-toolbar>

    <v-list>
      <v-list-group
        v-for="item in items"
        :key="item.title"
        v-model="item.active"
        :prepend-icon="item.action"
      >
        <template v-slot:activator>
          <v-list-item-header>
            <v-list-item-title v-text="item.title"></v-list-item-title>
          </v-list-item-header>
        </template>

        <v-list-item
          v-for="child in item.items"
          :key="child.title"
        >
          <v-list-item-header>
            <v-list-item-title v-text="child.title"></v-list-item-title>
          </v-list-item-header>
        </v-list-item>
      </v-list-group>
    </v-list>
  </v-card>
</template>

<script setup>
  const items = [
    {
      action: 'mdi-ticket',
      items: [{ title: 'List Item' }],
      title: 'Attractions',
    },
    {
      action: 'mdi-silverware-fork-knife',
      active: true,
      items: [
        { title: 'Breakfast & brunch' },
        { title: 'New American' },
        { title: 'Sushi' },
      ],
      title: 'Dining',
    },
    {
      action: 'mdi-school',
      items: [{ title: 'List Item' }],
      title: 'Education',
    },
    {
      action: 'mdi-human-male-female-child',
      items: [{ title: 'List Item' }],
      title: 'Family',
    },
    {
      action: 'mdi-bottle-tonic-plus',
      items: [{ title: 'List Item' }],
      title: 'Health',
    },
    {
      action: 'mdi-briefcase',
      items: [{ title: 'List Item' }],
      title: 'Office',
    },
    {
      action: 'mdi-tag',
      items: [{ title: 'List Item' }],
      title: 'Promotions',
    },
  ]
</script>

<script>
  export default {
    data: () => ({
      items: [
        {
          action: 'mdi-ticket',
          items: [{ title: 'List Item' }],
          title: 'Attractions',
        },
        {
          action: 'mdi-silverware-fork-knife',
          active: true,
          items: [
            { title: 'Breakfast & brunch' },
            { title: 'New American' },
            { title: 'Sushi' },
          ],
          title: 'Dining',
        },
        {
          action: 'mdi-school',
          items: [{ title: 'List Item' }],
          title: 'Education',
        },
        {
          action: 'mdi-human-male-female-child',
          items: [{ title: 'List Item' }],
          title: 'Family',
        },
        {
          action: 'mdi-bottle-tonic-plus',
          items: [{ title: 'List Item' }],
          title: 'Health',
        },
        {
          action: 'mdi-briefcase',
          items: [{ title: 'List Item' }],
          title: 'Office',
        },
        {
          action: 'mdi-tag',
          items: [{ title: 'List Item' }],
          title: 'Promotions',
        },
      ],
    }),
  }
</script>
