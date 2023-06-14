<template>
  <!-- HEADER -->
  <header>
    <div class="header_area">
      <div class="pad-15">
        <a @click="scroll_1()">분양개요</a>
        <a @click="scroll_2()">입지안내</a>
        <a @click="scroll_3()">단지안내</a>
        <a @click="scroll_4()">평명안내</a>
        <a @click="scroll_5()">프리미엄</a>
      </div>
    </div>
  </header>

  <!-- CONTENT AREA -->
  <!-- section 1 -->
  <section
    class="first_section"
    ref="scroll1">
    <img style="width: 100%;" src="../assets/main.png" alt="main" />
    <div class="body_content">
      <img src="../assets/1/2.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/3.jpg" alt="인천 더샵 아르테" />
    </div>
  </section>

  <!-- section 2 -->
  <section
    ref="scroll2">
    <div class="body_content">
      <img src="../assets/1/4.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/5.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/6.jpg" alt="인천 더샵 아르테" />
    </div>
  </section>

  <!-- section 3 -->
  <section
    ref="scroll3">
    <div class="body_content">
      <img src="../assets/1/7.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/8.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/9.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/10.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/11.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/12.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/13.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/14.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/15.jpg" alt="인천 더샵 아르테" />
    </div>
  </section>

  <!-- section 4 -->
  <section
    ref="scroll4">
    <div class="body_content">
      <img src="../assets/1/16.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/17.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/18.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/19.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/20.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/21.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/22.jpg" alt="인천 더샵 아르테" />
    </div>
  </section>

  <!-- section 5 -->
  <section
    ref="scroll5">
    <div class="body_content">
      <img src="../assets/1/46.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/47.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/48.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/49.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/50.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/51.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/52.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/53.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/54.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/55.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/56.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/57.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/58.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/59.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/60.jpg" alt="인천 더샵 아르테" />
      <img src="../assets/1/61.jpg" alt="인천 더샵 아르테" />
    </div>
  </section>

  <!-- SCROLL TOP BTN -->
  <div
    v-show="scY">
    <button
      class="scroll_top_btn"
      @click="toTopBtn">
      <img class="s-t-b_img" src="../assets/up-arrow.png" alt="arrow" />
    </button>
  </div>
</template>

<script setup>
import { loadFull } from "tsparticles";
const particlesInit = async engine => {
    await loadFull(engine);
};
const particlesLoaded = async container => {
    console.log("Particles container loaded", container);
};

console.log(particlesInit);
console.log(particlesLoaded);
</script>

<script>

export default {
  components: {

  },
  data() {
    return {
      stage: 1,
      scY: 0,
      scrollTimer: 0,
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      if (this.scrollTimer) return;
      this.scrollTimer = setTimeout(() => {
        this.scY = window.scrollY;
        clearTimeout(this.scrollTimer);
        this.scrollTimer = 0
      }, 200);
    },
    toTopBtn() {
      window.scrollTo({
        top: 0,
        behavior: "smooth"
      });
    },
    scroll_1() {
      const _this = this;
      _this.$refs.scroll1.scrollIntoView({ behavior: "smooth" });
    },
    scroll_2() {
      const _this = this;
      _this.$refs.scroll2.scrollIntoView({ behavior: "smooth" });
    },
    scroll_3() {
      const _this = this;
      _this.$refs.scroll3.scrollIntoView({ behavior: "smooth" });
    },
    scroll_4() {
      const _this = this;
      _this.$refs.scroll4.scrollIntoView({ behavior: "smooth" });
    },
    scroll_5() {
      const _this = this;
      _this.$refs.scroll5.scrollIntoView({ behavior: "smooth" });
    }
  }
}
</script>

<style lang="scss" scoped>


$primary: #69b3a2;
$primary1: #001140;
$primary2: #273D6B;
$primary3: #C9DBED;
$font : 'Montserrat', 'Helvetica Neue', Helvetica, Arial, sans-serif;
$font2: 'Roboto Slab', 'Helvetica Neue', Helvetica, Arial, sans-serif;

header { 
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: #001140;
  z-index: 1;
  .header_area {
    margin: 0 auto;
    max-width: 1140px;
    display: flex;
    justify-content: center;
    align-items: center;
    // padding: 10px 0;
    font-size: 14px;
    @media screen and (max-width: 1200px) {
      padding: 0 25px;
    }
    .pad-15 {
      color: #fff;
      font-weight: bold;
      font-family: $font !important;
      a {
        margin-right: 15px;
        &:last-child {          
          margin-right: 0;
        }
        &:hover {
          color: $primary3;
          cursor: pointer;
          padding-bottom: 8px;
          border-bottom: 3px solid $primary3;
        }
      }
    }
  }
}
.first_section {
  margin-top: 46px;
}
section {
  .body_content {
    text-align: center;
    img {
      width: 100%;
    }
  }

}

.scroll_top_btn {
  z-index: 3000;
  position: fixed;
  right: 30px;
  bottom: 40px;
  cursor: pointer;
  border-radius: 50%;
  width: 60px;
  height: 60px;
  background: none;
  padding: 0;
  .s-t-b_img {
    width: 100%;
  }
}
</style>