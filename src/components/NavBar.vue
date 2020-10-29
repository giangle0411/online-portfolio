<template>
  <div class="navbar">
    <div class="dropdown">
      <button class="dropbtn" @click="this.onDropDownClick">
        Dropdown
      </button>
      {{ this.dropDownShow }}
      <div v-show="dropDownShow" class="dropdown-content">
        <a href="#introduction" v-smooth-scroll>Introduction</a>
        <a href="#technologies" v-smooth-scroll>Skills</a>
        <a href="#">Tool and Technologies</a>
        <a href="#">Projects</a>
        <a href="#">Contact</a>
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
  height: 6vh;
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
}

.dropdown .dropbtn {
  cursor: pointer;
  font-size: 16px;
  border: none;
  outline: none;
  color: white;
  padding: 20px 16px;
  background-color: inherit;
  font-family: inherit;
  margin: 0;
}

.dropdown-content {
  position: fixed;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  z-index: 1;
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
  background-color: #ddd;
}

.show {
  display: block;
}
</style>
