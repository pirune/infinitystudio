<template>
  <div>
    <section class="intro">
      <div class="intro--image">
        <v-img :src="sec1_fullServices"></v-img>
        <div class="intro--logo-chipped">
          <div id="trigger--intro-logo"></div>
          <v-img :src="sec1_logoChipped" class="animated"></v-img>
        </div>
      </div>
      <div class="intro--text">
        <div id="trigger--intro-text" class="pa-10"></div>
        <div class="animated">
          <h1>Full Service<br>Digital Agency</h1>
          <div class="c2a"><v-btn color="secondary" large>Free Consult</v-btn></div>
        </div>
      </div>
    </section>

    <v-container>
      <section class="branding">
        <div class="branding--image">
          <div class="sec2-img1">
            <div id="trigger-img1" style="height: 100px"></div>
            <v-img :src="sec2_img1" contain height="auto" class="animated"></v-img>
          </div>
          <div class="sec2-img2">
            <div id="trigger-img2" style="height: 200px"></div>
            <v-img :src="sec2_img2" contain height="auto" class="animated"></v-img>
          </div>
          <div class="sec2-img3">
            <div id="trigger-img3" style="height: 200px"></div>
            <v-img :src="sec2_img3" contain max-height="250" class="animated"></v-img>
          </div>
        </div>
        <div class="branding--text">
          <h2>Branding & Identity</h2>
          <p>Create outstanding branding identity which increase your product value and make your customers remember you.</p>
          <ul>
            <li>Branding</li>
            <li>Coporate Identity</li>
            <li>Key Visual Design</li>
            <li>Create & Production</li>
            <li>Content Design</li>
          </ul>
          <div class="c2a"><v-btn color="secondary" large>Free Consult</v-btn></div>
        </div>
      </section>
    </v-container>

    <section class="development">
      <v-container>
        <h2>Web/App Design & Development</h2>
        <v-img :src="sec3_img" contain></v-img>
        <p>We understand your customer and create platform that match both your business needs and customers needs. Be data driven by tracking data and get closer to your goals.</p>
        <ul>
          <li>User Experince Design</li>
          <li>User Iterface Design</li>
          <li>Development</li>
        </ul>
        <div class="c2a"><v-btn color="secondary" large>Free Consult</v-btn></div>
      </v-container>
    </section>

    <v-container>
      <section class="marketing">
        <h2>Result Driven Marketing</h2>
        <v-img :src="sec4_img" contain></v-img>
        <p>Story Telling INCREASED CONVERSIONS, REPEAT TRAFFIC and Generating Greater VISIBILITY</p>
        <ul>
          <li>UMarketing Strategy</li>
          <li>Search Engine Optimization</li>
          <li>Social & Paid Ads</li>
          <li>Media & Content</li>
        </ul>
        <div class="c2a"><v-btn color="secondary" large>Free Consult</v-btn></div>
      </section>
    </v-container>
  </div>
</template>

<script>
export default {
  data () {
    return {
      sec1_fullServices: require('@/assets/images/home/full-services.png'),
      sec1_logoChipped: require('@/assets/images/home/logo-chipped.svg'),
      sec2_img1: require('@/assets/images/home/camera3.png'),
      sec2_img2: require('@/assets/images/home/camera1.png'),
      sec2_img3: require('@/assets/images/home/indent.png'),
      sec3_img: require('@/assets/images/home/development.png'),
      sec4_img: require('@/assets/images/home/marketing.png'),
    }
  },
  mounted() {
    var controller = new ScrollMagic.Controller();

    // Intro
    var scene = new ScrollMagic.Scene({triggerElement: "#trigger--intro-logo", duration: 0})
					.setTween(".intro--logo-chipped .animated", {right: '50px'})
					.addTo(controller);
    var scene = new ScrollMagic.Scene({triggerElement: "#trigger--intro-text", duration: 1500})
					.setTween(".intro--text .animated", {marginTop: '-350px'})
					.addTo(controller);

    // Branding
    var scene = new ScrollMagic.Scene({triggerElement: "#trigger-img1", duration: 500})
					.setTween(".sec2-img1 .animated", {marginTop: '-100px'})
					.addTo(controller);
    var scene = new ScrollMagic.Scene({triggerElement: "#trigger-img2", duration: 300})
					.setTween(".sec2-img2 .animated", {marginTop: '-150px'})
					.addTo(controller);
    var scene = new ScrollMagic.Scene({triggerElement: "#trigger-img3", duration: 400})
					.setTween(".sec2-img3 .animated", {marginBottom: '-30px'})
					.addTo(controller);
  },
  components: {
    
  }
}
</script>

<style lang="scss" scoped>
.intro {
  &--image {
    position: relative;
    margin-bottom: 80px;
    &::after {
      content: "";
      background-color: $color-dark;
      width: 80%;
      height: 100%;
      position: absolute;
      top: 25px;
      left: 0;
      z-index: -1;
    }
  }
  &--logo-chipped {
    width: 60%;
    max-width: 330px;
    position: absolute;
    left: 0px;
    bottom: -50px;
  }
  &--text {
    width: 100%;
    float: left;
    text-align: center;
    h1 {
      margin-bottom: 50px;
    }
  }
}
.branding {
  > div {
    float: left;
  }
  &--image {
    margin-top: 64px;
    width: 100%;
    height: 0;
    padding-top: 100%;
    float: left;
    position: relative;
    > div {
      position: absolute;
      &:first-child {
        top: 0;
        right: 32px;
        width: 40%;
      }
      &:nth-child(2) {
        top: 26%;
        left: 35%;
        width: 17%;
        z-index: 1;
      }
      &:last-child {
        bottom: 70px;
        left: 10%;
        width: 60%;
      }
    }
  }
}
.development {
  background-color: $color-dark;
}
ul {
  list-style: none;
  width: 100%;
  float: left;
  padding-left: 0;
  margin: 16px 0;
  color: $color-body;
  li {
    margin: 12px 0;
  }
}
</style>