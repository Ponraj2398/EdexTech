<template>
  <q-item
    clickable
    tag="a"
    target="_blank"
    :href="link"
  >
    <q-item-section
      v-if="icon"
      avatar>
      <q-icon class="text-blue-10" :name="icon" />
    </q-item-section>

    <q-item-section>
      <q-item-label class="text-dark">{{ title }}</q-item-label>
      <q-item-label class="text-dark" caption>{{ caption }}</q-item-label>
    </q-item-section>
  </q-item>

</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'EssentialLink',
  props: {
    title: {
      type: String,
      required: true
    },

    caption: {
      type: String,
      default: ''
    },

    link: {
      type: String,
      default: '#'
    },

    icon: {
      type: String,
      default: ''
    }
  },
})
</script>
