<template>
  <q-layout view="lHh Lpr lff">
    <q-header class="bg-secondary bg-transparent q-ma-xl">
      <q-toolbar>
        <div class="text-h6 text-italic text-primary la-belle-aurore-regular">Spark Studios</div>
        <q-space />
        <!-- nav btns -->
        <div class="row q-gutter-sm justify-center items-center">
          <q-btn
            v-for="link in linkList"
            :key="link.name"
            :label="link.name"
            :icon="link.icon"
            flat
            @click="$router.push(link.path)"
            class="text-primary"
          />
        </div>
      </q-toolbar>
    </q-header>

    <q-page-container class="bg-page q-ma-xl q-pa-xl">
      <router-view />
    </q-page-container>

    <q-footer class="bg-secondary q-ma-xl">
      <div class="text-caption">
        @2025 Spark Studios All Rights Reserved | <a href="">Privacy Policy</a>
      </div>
    </q-footer>
  </q-layout>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'HomeLayout',

  components: {},

  data() {
    return {
      linkList: [
        { name: 'Home', icon: 'home', path: '/' },
        { name: 'Workshops', icon: 'handyman', path: '/' },
        { name: 'Contact', icon: 'email', path: '/' },
      ],

      leftDrawerOpen: false,
    }
  },

  methods: {
    toggleLeftDrawer() {
      this.leftDrawerOpen = !this.leftDrawerOpen
    },
  },
})
</script>

<style>
.custom-padding {
  padding-top: 50px;
}

body {
  background-color: #dfdccd;
}
</style>
