<template>
  <div class="header">
    <div class="container-fluid" id="app">
      <nav class="row navbar">
        <div class="col-xs-6">
          <div class="hamburger-wrap">
            <button
              class="hamburger"
              type="button"
              @click="menuOpen = !menuOpen"
            >
              <transition name="fade">
                <span v-if="menuOpen" class="material-symbols-outlined absolute"
                  >close
                </span>
                <span v-else class="material-symbols-outlined absolute"
                  >menu
                </span>
              </transition>
            </button>
          </div>
        </div>
      </nav>
      <div class="row dropdown" :class="{ 'dropdown-after': menuOpen }">
        <ul class="navlist">
          <li class="navlistitem">
            <a href="#">home</a>
          </li>
          <li class="navlistitem">
            <a href="#">about</a>
          </li>
          <li class="navlistitem">
            <a href="#">contact</a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TheHeader",
  data() {
    return {
      menuOpen: false,
    };
  },
};
</script>

<style scoped>
.fade-enter-active {
  transition: opacity 0.3s ease-in-out;
}

.fade-leave-active {
  transition: opacity 0.3s ease-in-out;
}

.fade-enter-from {
  opacity: 0;
}
.fade-leave-to {
  opacity: 0;
}

button {
  border: none;
  position: relative;
}

.absolute {
  position: absolute;
  top: 13px;
  left: 12px;
}
.header {
  background-color: darkorange;
  text-align: center;
}

.navbar {
  height: 56px;
  background-color: Lightgrey;
  display: flex;
  border-radius: 0px;
}

.hamburger-wrap {
  width: 100px;
  height: 100%;
  margin-left: 50px;
  margin-right: 50px;
  display: flex;
  align-items: center;
}

.hamburger-wrap {
  float: right;
  justify-content: flex-end;
}

.hamburger {
  width: 48px;
  height: 48px;
  background-color: rgb(255, 255, 255);
}

.hamburger:focus {
  outline: none;
}

.dropdown {
  height: 0px;
  background-color: darkgoldenrod;
  transition: height 0.2s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.dropdown-after {
  height: 200px;
  transition: height 0.2s ease;
}

.navlist {
  list-style: none;
}

.navlistitem {
  text-transform: uppercase;
  text-align: center;
  padding: 20px;
}

.navlistitem a {
  color: #ffffff;
}
</style>
