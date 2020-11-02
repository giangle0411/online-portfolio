<template>
  <div class="navbar nav-container">
    <div class="dropdown-wrapper">
      <div class="dropdown" v-click-outside="closeDropDown">
        <button class="dropbtn" @click="this.onDropDownClick">
          Dropdown
        </button>
        <transition name="slide-fade">
          <div
            class="dropdown-content"
            @click="this.onDropDownClick"
            v-if="dropDownShow"
          >
            <a href="#introduction" v-smooth-scroll="{ updateHistory: false }"
              >Introduction</a
            >
            <a href="#skills" v-smooth-scroll="{ updateHistory: false }"
              >Skills</a
            >
            <a href="#projects" v-smooth-scroll="{ updateHistory: false }"
              >Projects</a
            >
            <a href="#contact" v-smooth-scroll="{ updateHistory: false }"
              >Contact</a
            >
          </div>
        </transition>
      </div>
    </div>
    <div class="right-icons">
      <div class="github-icon">
        Hello
      </div>
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
  padding-left: 150px;
  float: left;
  overflow: hidden;
  min-width: 160px;
  height: 70px;
  z-index: 100;
}

.dropdown .dropbtn {
  position: relative;
  cursor: pointer;
  font-size: 20px;
  border: none;
  outline: none;
  color: white;
  padding: 24px 16px;
  background-color: inherit;
  font-family: inherit;
  margin: 0;
  float: left;
  z-index: 150;
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
  color: white;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  text-align: left;
}

.dropdown-content a:hover {
  background-color: rgba(0, 49, 87, 0.1);
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
  padding-right: 150px;
  height: 50px;
  vertical-align: middle;
}

.right-icons .github-icon {
  display: inline-block;
  float: none;
}
</style>
