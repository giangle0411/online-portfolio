<template>
  <div class="navbar nav-container">
    <div class="dropdown-wrapper">
      <div class="dropdown" v-click-outside="closeDropDown">
        <div class="dropbtn" @click="this.onDropDownClick">
          <i class="fas fa-bars fa-2x"></i>
        </div>
        <transition name="slide-fade">
          <div
            class="dropdown-content"
            @click="this.onDropDownClick"
            v-if="dropDownShow"
          >
            <a href="#introduction" v-smooth-scroll="{ updateHistory: false }">
              <i class="far fa-id-card"></i>
              <div class="dropdown-item">Introduction</div>
            </a>
            <a href="#skills" v-smooth-scroll="{ updateHistory: false }">
              <i class="fas fa-glasses"></i>
              <div class="dropdown-item">Skills</div>
            </a>
            <a href="#projects" v-smooth-scroll="{ updateHistory: false }">
              <i class="fas fa-laptop-code"></i>
              <div class="dropdown-item">Projects</div>
            </a>
            <a href="#contact" v-smooth-scroll="{ updateHistory: false }">
              <i class="fas fa-paper-plane"></i>
              <div class="dropdown-item">Contact</div>
            </a>
          </div>
        </transition>
      </div>
    </div>

    <div class="right-icons">
      <a href="mailto:giangle0411@gmail.com" class="email-icon nav-icon">
        <i class="far fa-envelope fa-3x"></i>
      </a>
      <a
        href="https://www.linkedin.com/in/giangle0411/"
        class="linkedin-icon nav-icon"
      >
        <i class="fab fa-linkedin fa-3x"></i>
      </a>
      <a href="https://github.com/giangle0411" class="github-icon nav-icon">
        <i class="fab fa-github fa-3x"></i>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dropDownShow: false
    }
  },
  methods: {
    onDropDownClick() {
      this.dropDownShow = !this.dropDownShow
    },
    closeDropDown() {
      this.dropDownShow = false
    }
  }
}
</script>

<style lang="scss" scoped>
.navbar {
  position: fixed;
  width: 100%;
  height: 70px;
  background-image: linear-gradient(rgba(0, 49, 87, 0.8), rgba(0, 49, 87, 0.1));
  font-family: Arial, Helvetica, sans-serif;
}

.dropdown {
  float: left;
  overflow: hidden;
  min-width: 300px;
  height: 100%;
  z-index: 100;
}

.dropdown .dropbtn {
  position: relative;
  cursor: pointer;
  font-size: 21px;
  border: none;
  outline: none;
  color: rgba(255, 255, 255, 0.8);
  padding: 14px;
  background-color: inherit;
  font-family: inherit;
  margin: 0;
  float: left;
  z-index: 150;
}

.dropdown .dropbtn:hover {
  color: rgba(255, 255, 255, 1);
}

.dropdown-content {
  transition: opacity 1s ease-out;
  position: fixed;
  top: 0px;
  padding-top: 70px;
  min-width: 300px;
  background-color: rgba(0, 49, 87, 0.5);
}

.dropdown-content a {
  float: none;
  color: rgba(255, 255, 255, 0.8);
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  text-align: left;
}

.dropdown-content a:hover {
  background-color: rgba(0, 49, 87, 0.1);
  color: rgba(255, 255, 255, 1);
}

.dropdown-item {
  display: inline-block;
  margin-left: 10px;
}

.slide-fade-enter-active {
  transition: all 0.5s ease;
}
.slide-fade-leave-active {
  transition: all 0.5s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateY(-10px);
  opacity: 0;
}

.right-icons {
  float: right;
  height: 100%;
  position: relative;

  font-size: 14px;
  margin: 14px 0px;
  padding-left: 20px;
}

.right-icons a {
  color: rgba(255, 255, 255, 0.8);
}

.right-icons a:hover {
  color: rgba(255, 255, 255, 1);
}

.nav-icon {
  display: inline-block;
  margin-left: 20px;
}
</style>
