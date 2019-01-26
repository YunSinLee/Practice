<template>
  <div id="main-page">
    <div id="bgimg0" class="bgimg"></div>
    <div class="wrap">
      <div class="contents">
        <div class="title">
          <p class="main white font-700">개그, 하세요</p>
          <p class="sub white white font-500">이윤신과 함께</p>
        </div>
        <div class="subtitle white font-500">인싸가 되고 싶은 여러분들을 위한 서비스</div>
        <div class="btn-start white font-500">
          <p>시작하기</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    this.changeBgImg();
  },
  methods: {
    // changeBgImg() {
    //   for (let num = 0; num < 3; num++) {
    //     (function(x) {
    //       setTimeout(function() {
    //         console.log("bgimg" + num);
    //         document.getElementById("bgimg" + num).id = "bgimg" + (num + 1);
    //       }, 1000 * (x + 1));
    //       if (num == 3) {
    //         num = 0;
    //       }
    //     })(num);
    //   }
    // }
    changeBgImg() {
      setInterval(() => {
        document.getElementsByClassName("bgimg")[0].id =
          "bgimg" + Math.floor(Math.random() * 4);
      }, 10000);
    }
  }
};
</script>

<style src="../assets/css/main_page.css">
</style>
