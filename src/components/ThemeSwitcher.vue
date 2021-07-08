<template>
  <div v-if="enabled">
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
</template>

<script>

export default {
  name: 'ThemeSwitcher',
  components: {
  },
  props: {
    enabled: {
      type: Boolean,
      default: false
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
