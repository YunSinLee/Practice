<template>
  <div id="app">
    <!-- <ul id="menu">
      <li data-menuanchor="page1" class="active">
        <a href="#page1">First slide</a>
      </li>
      <li data-menuanchor="page2">
        <a href="#page2">Second slide</a>
      </li>
    </ul>-->
    <div id="fullPage-nav">
      <ul>
        <li data-tooltip></li>
        <li data-tooltip></li>
      </ul>
    </div>
    <Header
      :isWhite="isWhite"
      style="position:fixed; top:0; left:50%; transform:translate(-50%,0); z-index:2;"
    />
    <full-page ref="fullpage" :options="options" id="fullpage">
      <div class="section">
        <MainPage/>
      </div>
      <div class="section">
        <ExpPage/>
      </div>
    </full-page>
  </div>
</template>

<script>
import Header from "./components/header.vue";
import MainPage from "./components/mainPage.vue";
import ExpPage from "./components/expPage.vue";

export default {
  name: "app",
  data() {
    return {
      options: {
        menu: "#menu",
        anchors: ["page1", "page2"],
        navigationPosition: "right",
        navigation: true,
        // navigationTooltips: ["firstSlide", "secondSlide"],
        afterLoad: this.afterLoad,
        v2compatible: true
      },
      isWhite: true
    };
  },
  components: {
    Header,
    MainPage,
    ExpPage
  },
  methods: {
    afterLoad(origin, destination, direction) {
      console.log(origin, destination, direction);
      if (destination.index > 0) {
        this.isWhite = false;
      } else {
        this.isWhite = true;
      }
      console.log(this.isWhite);
    }
  }
};
</script>

<style src="./assets/css/base.css">
</style>
