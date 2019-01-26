<template>
  <div id="header" class>
    <div class="logo-group" :class="[isWhite ? activeClass : '', errorClass]">
      <div class="logo"></div>
      <div class="ap-logo"></div>
      <div class="aq-logo"></div>
    </div>
    <div class="menu" :class="[isWhite ? activeClass : '', errorClass]">
      <div class="login">로그인</div>
      <div class="join">가입하기</div>
      <div class="intro">서비스소개</div>
      <div class="email">이메일</div>
      <div class="lang" @click="sayHI()">언어</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeClass: "white",
      errorClass: "black"
    };
  },
  props: {
    isWhite: {
      type: Boolean
    }
  },
  methods: {
    sayHI() {
      console.log(this.isWhite);
    }
  }
};
</script>

<style src="../assets/css/header.css">
</style>
