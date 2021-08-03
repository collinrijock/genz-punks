<template>
  <div id="app">
    <div id="landing">
      <header>
        <h1>Gen Z Punks</h1>
        <div id="socials">
          <img class="icon" src="./assets/logo.png"></img>
          <img class="icon" src="./assets/logo.png"></img>
          <img class="icon" src="./assets/logo.png"></img>
          <img class="icon" src="./assets/logo.png"></img>
        </div>
      </header>
      <h3>What are GenZ Punks?</h3>
      <p>10,000 unique collectible characters with proof of ownership stored on the Ethereum blockchain. The project that inspired the modern CryptoArt movement. Selected press and appearances include Mashable, CNBC, The Financial Times, Bloomberg, MarketWatch, The Paris Review, Salon, The Outline, BreakerMag, Christie's of London, Art|Basel, The PBS NewsHour, The New York Times in 2018 and again in 2021. The Cryptopunks are one of the earliest examples of a "Non-Fungible Token" on Ethereum, and were inspiration for the ERC-721 standard that powers most digital art and collectibles.</p>
      <h3>How do I get a punk?</h3>   
      <p>10,000 unique collectible characters with proof of ownership stored on the Ethereum blockchain. The project that inspired the modern CryptoArt movement. Selected press and appearances include Mashable, CNBC, The Financial Times, Bloomberg, MarketWatch, The Paris Review, Salon, The Outline, BreakerMag, Christie's of London, Art|Basel, The PBS NewsHour, The New York Times in 2018 and again in 2021. The Cryptopunks are one of the earliest examples of a "Non-Fungible Token" on Ethereum, and were inspiration for the ERC-721 standard that powers most digital art and collectibles.</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
  }
}
</script>

<style lang="scss">
@import './global.scss';
@import './assets/fonts.css';
#app {
  @extend .clear;
  font-family: $font;
  min-width:100vw;
  min-height: 100vh;
  @extend .flex-column;
  justify-content: flex-start;
  #landing {
    width:80vw;
    header {
      @extend .flex-row;

      h1 {
        font-size:50px;
        color: color(red)
              }
      #socials {
        width: 25%;
        margin-left: auto;
        @extend .flex-row;
        justify-content: space-between;
        .icon {
          height: 40px;
          width: 40px;
          @extend .button;
        }
      }
    }
    p {
      font-family: $font2;
      width: 60%;
    }
  }
}
</style>
