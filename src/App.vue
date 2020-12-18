<template>
  <div id="app">
    <TweetsContainer>
      <Tweets />
    </TweetsContainer>
  </div>
</template>

<script>

import Tweets from './components/Tweets'
import TweetsContainer from './components/TweetContainer'

export default {
  name: 'App',

  components: {
    Tweets,
    TweetsContainer,
  }
}
</script>

<style lang="scss">


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
