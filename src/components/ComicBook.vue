<template>
  <body>
  <div class="strip">
    <h1>Peanuts comic strip paintings from the 50's</h1>
    <h2>4 panels of Linus</h2>
    <h3>Painting's by <cite>
      <a href="https://www.etsy.com/listing/63492282/peanuts-comic-strip-paintings-from-the" target="_blank">Walter Yablonsky</a>
    </cite></h3>
    <h4>Original strip by <cite>Charles Schulz</cite></h4>
      <div>
        <figure>
       <img @mouseover="changeImage" :src="current">
          <figcaption>Hover over each image to cycle through all four images in this series</figcaption>
        </figure>
      </div>
  </div>
  <div class="strip">
    <h1>Curtis by Ray Billingsley</h1>
    <h2>This strip was written during the COVID-19 shutdown</h2>
      <div class="container">
        <img class="item1" v-show="c1" :src="cFirst">
        <img class="item2" v-show="c2" :src="cSecond">
        <img class="item3" v-show="c3" :src="cThird">
        <img class="item4" v-show="c4" :src="cFourth">
      </div>
    <div>
      <input id="curtis-controller" type="button" value="Start Curtis Slideshow" @click="slideShow">
    </div>
  </div>
  </body>
</template>

<script>

import linus1 from "../assets/linus1.png";
import linus2 from "../assets/linus2.png";
import linus3 from "../assets/linus3.png";
import linus4 from "../assets/linus4.png";
import curtis1 from "../assets/curtis1.png";
import curtis2 from "../assets/curtis2.png";
import curtis3 from "../assets/curtis3.png";
import curtis4 from "../assets/curtis4.png";

export default {
  name: "ComicBook",
  data() {
    return {
      current: null, // pointer to current Linus
      first: linus1,
      second: linus2,
      third: linus3,
      fourth: linus4,
      cCurrent: null, // pointer to current Curtis
      cFirst: curtis1,
      c1: false,
      cSecond: curtis2,
      c2: false,
      cThird: curtis3,
      c3: false,
      cFourth: curtis4,
      c4: false,
    }
  },
  methods: {
    changeImage() {
      if(this.current === this.first) {
        this.current = this.second;
      } else if (this.current === this.second) {
        this.current = this.third;
      } else if (this.current === this.third) {
        this.current = this.fourth;
      } else { // this.current === this.fourth
        this.current = this.first;
      }
    },
    slideShow(){
      document.getElementById('curtis-controller').value = "next frame";
      if (this.cCurrent === null) {
        this.cCurrent = this.cFirst;
        this.c1 = true; // show c1
      } else if (this.cCurrent === this.cFirst) {
        this.c1 = false;
        this.cCurrent = this.cSecond;
        this.c2 = true;
      } else if (this.cCurrent === this.cSecond) {
        this.c2 = false;
        this.cCurrent = this.cThird;
        this.c3 = true;
      } else if (this.cCurrent === this.cThird) {
        this.c3 = false;
        this.cCurrent = this.cFourth;
        this.c4 = true;
        document.getElementById('curtis-controller').value = "start over";
      } else if (this.c4) { // case that fourth in Curtis series is showing
        this.c4 = false;
        this.cCurrent = this.cFirst;
        this.c1 = true;
      }
    }
  },
  created() {
    this.current = this.first;
  }
}
</script>

<style scoped>
@import "../styles/style.css";
</style>