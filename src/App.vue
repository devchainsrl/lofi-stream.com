<template>
  <div
    id="app"
    :class="'theme theme-' + selectedTheme"
  >
    <div id="inspire">
      <Header
        id="header"
      />
      <StreamContainer
        id="streamContainer"
        :streams="streams"
        :selected-stream-index="selectedStreamIndex"
      />
      <Footer
        id="footer"
        :streams="streams"
        :themes="supportedThemes"
        @switchChannel="switchChannel"
        @switchTheme="switchTheme"
      />
    </div>
  </div>
</template>

<script>

import Footer from './components/Footer.vue'
import Header from './components/Header.vue'
import StreamContainer from './components/StreamContainer.vue'

export default {
  components: { Header, Footer, StreamContainer },
  data: () => {
    return {
      selectedStreamIndex: 0,
      selectedTheme: 'gold',
      supportedThemes: [
        'sea', 'violet', 'blue', 'white'
      ],
      streams: [
        {
          name: 'lofi hip hop radio - beats to relax/study to',
          src: 'https://www.youtube.com/embed/jfKfPfyJRdk?autoplay=1',
          type: 'youtube'
        },
        {
          name: 'coffee shop radio // 24/7 lofi hip-hop beats',
          src: 'https://www.youtube.com/embed/5KAN9_CzSA?autoplay=1',
          type: 'youtube'
        }
      ]
    }
  },
  methods: {
    switchChannel (channelIndex) {
      this.selectedStreamIndex = channelIndex
    },
    switchTheme (themeName) {
      if (this.supportedThemes.includes(themeName)) {
        this.selectedTheme = themeName
      }
    }
  }

}
</script>

<style>
body {
    padding: 0;
    margin: 0;
}
#inspire {
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: flex-start;
    height: 100vh;
}
#app {
    background-color: var(--ls-primary);
    width: 100%;
    height: 100%;
    margin: 0;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: var(--ls-light-text);
}
#header, #footer {
    display: block;
}
#streamContainer {
    display: flex;
    flex:2;
}
</style>
