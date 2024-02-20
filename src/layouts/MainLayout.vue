<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="bg-white">
      <q-toolbar>
        <q-btn flat dense round icon="menu" style="color:#000;" aria-label="Menu" @click="toggleRightDrawer" />

        <q-toolbar-title>
          <strong><span style="color: rgb(235,49,51);">Edex</span> <span
              style="color: rgb(35,82,157);">Tech</span></strong>
        </q-toolbar-title>
        <div class="q-gutter-lg">
          <!-- <q-btn class="glossy" color="deep-orange" label="Apply Now" /> -->
          <q-btn color="deep-orange" class="glossy" label="SIGN IN" />
        </div>
      </q-toolbar>
    </q-header>
    <!-- <q-footer style="background-color: aqua;">
    </q-footer> -->
    <q-drawer v-model="rightDrawerOpen" side="right" bordered style="min-height: auto;background-color: antiquewhite;">
      <q-list>
        <q-item-label header>
          <q-input v-model="search" filled type="search" label="Search..">
            <template v-slot:append>
              <q-icon name="search" style="margin-bottom: 25px;" />
            </template>
          </q-input>
        </q-item-label>

        <EssentialLink v-for="link in essentialLinks" :key="link.title" v-bind="link" />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Home',
    // caption: 'quasar.dev',
    icon: 'home',
    link: 'https://quasar.dev'
  },
  {
    title: 'Career',
    // caption: 'github.com/quasarframework',
    icon: 'school',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'About Us',
    // caption: 'chat.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Contact',
    caption: '+91-8095570001',
    icon: 'phone',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'FAQ',
    // caption: '@quasarframework',
    icon: 'help_center',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: 'EdexTech',
    icon: 'facebook',
    link: 'https://facebook.quasar.dev'
  },
  // {
  //   title: 'Instagram',
  //   caption: 'edextech_it',
  //   icon: 'instagram',
  //   link: 'https://awesome.quasar.dev'
  // }
]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup() {
    const rightDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      rightDrawerOpen,
      toggleRightDrawer() {
        rightDrawerOpen.value = !rightDrawerOpen.value
      }
    }
  }
})
</script>
