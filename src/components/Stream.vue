<template>
  <div>
    Current Stream: <span class="stream-name">{{ stream.name }}</span>
    <iframe
      v-if="stream.type === 'youtube'"
      class="stream-player stream-player-youtube"
      :src="stream.src"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
      allowfullscreen
    />
  </div>
</template>

<script>
export default {
  name: 'Stream',
  props: {
    stream: {
      type: Object,
      required: true
    }
  },
  computed: {},
  watch: {},
  methods: {}
}
</script>

<style scoped>
.stream-player {
    height: inherit;
    border: 0;
    margin: 0;
    display: flex;
    flex-grow: 2;
    vertical-align: auto;
}

.stream-player-youtube {
    width: 100vw;
    min-height: calc(100vh - 256px);
    height: calc(100vh - 150px)
}

.stream-name {
    color: var(--ls-light-text);
}
</style>
