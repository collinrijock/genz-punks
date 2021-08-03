<template>
  <div id="app">
    <div id="landing">
      <header>
        <img id="randompunk" :src=url>
        <h1>Gen Z Punks</h1>
        <div id="socials">
          <a href="https://discord.gg/ym2RcqgfFC" target="_blank" rel="noreferrer noopener"><img class="icon" src="./assets/discord.svg"></img></a>
          <a href="https://twitter.com/genzpunks" target="_blank" rel="noreferrer noopener"><img class="icon" src="./assets/twitter.svg"></img></a>
          
        </div>
      </header>
      <div id="main">
        <div id="text">
          <h3>What are GenZ Punks?</h3>
          <p>A Gen Z Punk is a 24x24 pixel art that is randomly generated from a pool of traits. We're heavily inspired by CryptoPunks,
             an ETH token that kicked off the punk community. These images are NFTs, meaning that your Gen Z Punk is unique and belongs to only you.</p>
          
          <h3>How can I get started?</h3>   
          <p>Getting started with Gen Z Punks couldnt be easier.</p>
          <li>Download and install a Chrome browser plugin called MetaMask. This will allow websites (that you authorize) access to your Ethereum account.</li>
          <br>
          <li>If you made a new account, buy some Ether. The MetaMask plugin has a button that will allow you to buy Ether from Coinbase.</li>
          <br>
          <li>Once you have the plugin installed, this website will recognize it and add buttons that allow you to bid on, buy and sell punks directly in the interface.</li>
          <br>
          <li>For example, you can buy Punk #6085 for 33.1 ETH ($82,660.63 USD).</li>
          
          <h3>About Gen Z Punks</h3>
          <p>Gen Z Punks was started as a hackathon idea for the first ever Miami Hack Week (shoutout to them).</p>
          
          <h3>Technical details</h3>
          <li>The actual images of the punks are too large to store on the blockchain, so we took a hash of the composite image of all the punks and embeded it into the contract. You can verify that the punks being managed by the Ethereum contract are the True Official Genuine CryptoPunks™ by calculating an SHA256 hash on the cryptopunks image and comparing it to the hash stored in the contract.</li>
          <br>
          <li>CryptoPunks are almost an ERC20 token. We support the methods that provide your balance so you can watch CryptoPunks as a token in your wallet and see how many you own. None of the other methods are the same since you're not transferring a simple balance, but need to reference which specific Punk you want to work with.</li>
          <br>
          <li>The contract source and more technical details are available on Github.</li>

        </div>
        <div id="viewer">
          <h3>Meet the Punks</h3>
          <PunkViewer></PunkViewer>
        </div>
      </div>
      
      
    </div>
  </div>
</template>

<script>
import PunkViewer from "./PunkViewer.vue"
export default {
  name: 'App',
  data() {
    return {
      url: "",
      urls: ["https://s3.cointelegraph.com/uploads/2021-04/96eb5cdb-7629-49c4-966f-1a9ea0c0a274.png","data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAA5FBMVEX///8AAADbsYDluYafn58pIRj/ySbb29srKytLS0u9mG7RqXrny6nhtoRzXUP6+vqOc1OmhmH/2SY8PDzq6up/f39TQzG5ublYWFjy1LHYr4Xfu4/Kysr/yxrzwU4TExPes3uvmoDkxqHtvVr9xy/oumbjtnF5a1ncuyH/4SdhUg7CpR2GaRT4xD/crSEwKQdiYmIcHBwoKCgjHBRgTjioqKiKb1G7l3G8vLyQkJBSUlJcUUP83rhFNyh0dHQ2LCA7P0tsVz/mzVp4ZC4iGAAnHgDQultKPwuzqZ3KwbfVqTfRpkPEYMG7AAADl0lEQVR4nO3daVfaQBSAYQkiiA1KtYp7tbUtXV3QWrtau/f//5+eHuZOxBuGQJQZwvt+hAnkOejJEIYwM0NEREREREREREREREREREREREREFGaLufMtGFRrPmdrvgWDapVyhtB7CBEi9B/CgZ37FqRXnTWdHuYVvpOHmvWN6ql6lBemu/CN6qlau31hyzeqJ4QIEfoP4cQKq9K5Fr5/KjWkXYenI4NW5ZZD++gr/oSzRzWTPuLvrZv2Y1O54hDWy2ZQU26Rhz5ernoUOnZ5755pPzK5hWZQ3FR3HRdeWEOIECFChInQMXqChB/kQL8ZqcrSkoyu2JvsoNjeFKhwXV66FKFFXBP2H4UQIUKECBFOrnBT6r/rEy507DJChAgRIkQ4kvBkYoSVVdPHTMKmDO/EkyJs6LMRTqKMdgBDE7p2dcQQIkSIEGHhhOU7yJ9w8YH0SXZit3IHWaF9vtNxCedLnhrXklOECBEiRIhwGGFjSZVpTzt6u89hCmXJZJJzRYltSW+3OngrL8L+02W3UE3UESJEiBDhdAnlHXrKlyvkrhMtjDsncqfazOd7fC1MVlg2tNDemXLeyn6UEcL6UqfQ7nGKcKH/8GQ7hAgRIkRYDOHMFyvsf4CLLydPmFwZ4usz05WsqdCTlGihrsoAvL7d2IVb8ozf2ve7tZ/LTcX4dG1LZppvECJEiBDhyEJ5xu/tdl7hzVPeccr24xdW10znP16Yfo4orDdVer7jc7WJnbWVRhPGZ+oBXCe1fM68RxWmfEKFECFChAiLJmxJ9jKQw30bIfjjYdKp3tNsRL2YVA8KQjjit4KyhRAhQoQIESJEiBAhQoQIEYYstOsMUhZe6LULdcfwUIW2pl4l67qed6DnaYYUZrlCK0KECBEinHbhJB8PL6OFm6k9jvQY5/CwhI3bm46GKizEmiiECBFOsTCI3wpqxBum/DJZj7lZ2u0WxGt49UjKTayfdS8jcfZrS/L5m10ifLkt5RUm35kJ4lc6rwnnut2iMIhflkOIEKH/EBZJOPe421z00JTstOutve63vUaEb93/kllbJLM2e+g/EKD9Lmi2wvr1eD3z3rB/rggRhhFChAj9lya0x0M5Qr6VQbXlDNVCF0ZPpJ1Xpj8y6GIlU75RPTnOtW3smL/X7dcyaH7R9/4On1No/iHnEAYdQoThN+XCoh8tooMd09+iCiM1ayucUKojDDmECMMPIcKx9Q8ynusYv/sf8QAAAABJRU5ErkJggg==","https://dappimg.com/media/image/app/6d8fc8150ce04166b6e506074f43c3c4.jpg"],
    }
  },
  created() {
    while(true) {
      this.urls.forEach((item,index)=> {
        this.url = item;
        console.log(item)
      });
    }
  },
  components: {
    PunkViewer
  }
}
</script>

<style lang="scss">
@import './global.scss';
@import './assets/fonts.css';
#app {
  @extend .clear;
  font-family: $font;
  color: #23272A;
  min-width:100vw;
  min-height: 100vh;
  @extend .flex-column;
  justify-content: flex-start;
  font-size: 16px;

  #landing {
    width:80vw;
    height: 100%;
    header {
      @extend .flex-row;
      height: 100%;

      #randompunk {
        height: 10vh;
      }
      h1 {
        @extend .clear;
        padding: 5vh 0;
        font-size:7vw;
        color: color(red)
      }

      #socials {
        height: 100%;
        width: 15%;
        margin-left: auto;
        @extend .flex-row;
        justify-content: space-around;

        .icon {
          max-height: 40px;
          @extend .button;
        }
      }
    }
    #main {
      @extend .flex-row;
      justify-content: space-between;
      align-items: flex-start;
      height: 100%;
      position: relative;
      padding-bottom: 10vh;

      #text {
        list-style-position: inside;
        height: 100%;
        max-width: 50%;
        h3 {
          font-size: 2vw;
        }
        p {
          font-family: $font2;
          width: 60%;
        }
      }
      #viewer {
        @extend #text;
        @extend .flex-column;
        width: 40vw;
        height: 100%;
      }
    }
  }
}
</style>
