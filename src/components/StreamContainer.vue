<template>
  <div class="stream-container">
    <div
      v-for="(stream, index) in streams"
      :key="index"
    >
      <Stream
        v-if="index === selectedStreamIndex"
        :stream="stream"
      />
    </div>
  </div>
</template>

<script>
import Stream from './Stream.vue'

export default {
  name: 'StreamContainer',
  components: { Stream },
  props: {
    selectedStreamIndex: {
      type: Number,
      required: true
    },
    streams: {
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
.stream-container {
    width: 100vw;
    height: 100%;
    margin: 0;
    background-color: var(--ls-dark-background);
    color: var(--ls-gray-text);
    /*
    background-image: url('https://media.tenor.com/images/a742721ea2075bc3956a2ff62c9bfeef/tenor.gif');
    background-size: 40px;
    background-position: center;
    background-repeat: no-repeat;
    */
}
</style>
