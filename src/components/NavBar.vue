<template>
  <div class="navbar">
    <div class="dropdown-wrapper">
      <div class="dropdown" v-click-outside="closeDropDown">
        <button class="dropbtn" @click="this.onDropDownClick">
          Dropdown
        </button>
        {{ this.navShow }}
        <div
          class="dropdown-content"
          @click="this.onDropDownClick"
          v-if="dropDownShow"
          style="display: `${this.navShow}`"
        >
          <a href="#introduction" v-smooth-scroll="{ updateHistory: false }"
            >Introduction</a
          >
          <a href="#skills" v-smooth-scroll>Skills</a>
          <a href="#">Projects</a>
          <a href="#">Contact</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dropDownShow: false,
      navShow: 'none'
    }
  },
  methods: {
    onDropDownClick() {
      this.dropDownShow = !this.dropDownShow
      if (this.navShow === 'none') {
        this.navShow = 'block'
      } else {
        this.navShow = 'none'
      }
    },
    closeDropDown() {
      this.dropDownShow = false
      this.navShow = 'none'
    }
  }
}
</script>

<style lang="scss" scoped>
.navbar {
  overflow: hidden;
  position: fixed;
  top: 0;
  width: 100%;
  height: 50px;
  background-image: linear-gradient(rgba(0, 49, 87, 0.8), rgba(0, 49, 87, 0.1));
  font-family: Arial, Helvetica, sans-serif;
}

.navbar a {
  float: left;
  font-size: 16px;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

.dropdown {
  float: left;
  overflow: hidden;
  min-width: 160px;
  z-index: 100;
}

.dropdown .dropbtn {
  position: relative;
  cursor: pointer;
  font-size: 16px;
  border: none;
  outline: none;
  color: white;
  padding: 16px 16px;
  background-color: inherit;
  font-family: inherit;
  margin: 0;
  z-index: 150;
}

.dropdown-content {
  position: fixed;
  top: 0px;
  padding-top: 50px;
  min-width: 300px;
  background-color: rgba(0, 49, 87, 0.5);
  transition-duration: 0.5s;
}

.dropdown-content a {
  float: none;
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  text-align: left;
}

.dropdown-content a:hover {
  background-color: rgba(0, 49, 87, 0.1);
}

.show {
  display: block;
}
</style>
