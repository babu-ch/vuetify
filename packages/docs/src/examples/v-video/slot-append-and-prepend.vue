<template>
  <div class="d-flex justify-center">
    <v-video
      :start-at="10"
      class="align-self-center"
      image="https://jsek.work/vt-sunflowers.jpg"
      src="https://jsek.work/vt-sunflowers.mp4"
      eager
      muted
    >
      <template v-slot:prepend>
        <v-icon-btn icon="mdi-skip-next"></v-icon-btn>
      </template>
      <template v-slot:append>
        <v-icon-btn icon="mdi-closed-caption"></v-icon-btn>
        <v-icon-btn icon="mdi-cog"></v-icon-btn>
        <v-icon-btn icon="mdi-picture-in-picture-bottom-right"></v-icon-btn>
        <v-icon-btn icon="mdi-cast"></v-icon-btn>
      </template>
    </v-video>
  </div>
</template>
