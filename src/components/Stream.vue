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
  width: 100vw;
  border: 0;
  height: 100%;
}

.stream-name {
    color: var(--ls-primary);
}
</style>
