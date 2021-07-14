<template>
  <div>
    <div class="footer-section channel-switcher">
      Channel Switcher:
      <div
        v-for="(stream, index) in streams"
        :key="index"
      >
        <button @click="() => $emit('switchChannel', index)">
          #{{ index }}: {{ stream.name }}
        </button>
      </div>
      <ThemeSwitcher
        :themes="themes"
        class="theme-switcher"
        @switchTheme="$emit('switchTheme', $event)"
      />
    </div>
  </div>
</template>

<script>

import ThemeSwitcher from './ThemeSwitcher.vue'
export default {
  name: 'Footer',
  components: {
    ThemeSwitcher
  },
  props: {
    streams: {
      type: Array,
      required: true
    },

    themes: {
      type: Array,
      required: true
    }
  },
  computed: {},
  watch: {},
  methods: {}
}
</script>

<style scoped>

</style>
