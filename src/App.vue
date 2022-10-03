<template>
  <div>
    <h3>Toggle switch {{ isEnabled ? "ON" : "OFF" }}</h3>
    <div
      @click="toggleSwitch"
      :class="{
        'np-outer-switch': true,
        'np-outer-switch-on': isEnabled,
        'np-outer-switch-off': !isEnabled,
      }"
    >
      <div
        :class="{
          'np-inner-switch': true,
          'np-inner-switch-left': !isEnabled,
          'np-inner-switch-right': isEnabled,
        }"
      ></div>
    </div>
  </div>
  <!--
    www.nightprogrammer.com
  -->
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      isEnabled: false,
    };
  },
  methods: {
    toggleSwitch() {
      this.isEnabled = !this.isEnabled;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #0066ff;
  margin: 60px;
  max-width: 400px;
}
h3 {
  text-align: left;
}
.np-outer-switch {
  width: 70px;
  height: 34px;
  border-radius: 30px;
  background: rgb(212, 212, 212);
  cursor: pointer;
  position: relative;
}

.np-outer-switch-off {
  background: rgb(212, 212, 212);
  transition: background 0.4s;
}

.np-outer-switch-on {
  background: rgb(0, 202, 51);
  transition: background 0.4s;
}

.np-inner-switch {
  height: 30px;
  width: 30px;
  background: #fff;
  border-radius: 50%;
  position: absolute;
  top: 2px;
  left: 2px;
}

.np-inner-switch-left {
  top: 2px;
  left: 2px;
  transition: left 0.4s;
}

.np-inner-switch-right {
  top: 2px;
  left: 38px;
  transition: left 0.4s;
}
</style>
