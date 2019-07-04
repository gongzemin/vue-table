<template>
  <div id="app">
    <HelloWorld :data="gridData" :columns="gridColumns" msg="Hello Vue in CodeSandbox!"/>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",
  components: {
    HelloWorld
  },
  data() {
    return {
      gridData: [
        { name: "翠翠", location: "湘西" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" },
        { name: "American alligator", location: "Southeast United States" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" },
        { name: "American alligator", location: "Southeast United States" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" },
        { name: "American alligator", location: "Southeast United States" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" },
        { name: "American alligator", location: "Southeast United States" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" },
        { name: "American alligator", location: "Southeast United States" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" },
        { name: "American alligator", location: "Southeast United States" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" },
        { name: "American alligator", location: "Southeast United States" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" },
        { name: "American alligator", location: "Southeast United States" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" },
        { name: "American alligator", location: "Southeast United States" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" },
        { name: "American alligator", location: "Southeast United States" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" },
        { name: "American alligator", location: "Southeast United States" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" },
        { name: "American alligator", location: "Southeast United States" },
        { name: "Chinese alligator", location: "Eastern China" },
        { name: "Spectacled caiman", location: "Central & South America" },
        { name: "Broad-snouted caiman", location: "South America" },
        { name: "Jacaré caiman", location: "South America" },
        { name: "Black caiman", location: "South America" }
      ],
      gridColumns: [{ name: "名字" }, { location: "地点" }]
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
