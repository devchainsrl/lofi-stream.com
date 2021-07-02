<template>
  <div>
    <div class="channel-switcher">
      Channel Switcher:
      <div
        v-for="(stream, index) in streams"
        :key="index"
      >
        <button @click="() => $emit('switchChannel', index)">
          #{{ index }}: {{ stream.name }}
        </button>
      </div>
      <div
        class="theme-switcher"
      >
        <div class="text-amber">
          Themes
        </div>
        <div
          v-for="(theme, index) in themes"
          :key="index"
        >
          <button
            :class="'btn-theme theme-' + theme"
            @click="() => $emit('switchTheme', theme)"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Footer',
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
