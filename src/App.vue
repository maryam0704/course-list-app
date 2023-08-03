<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <!-- hello world is the component made here -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <h1>list of courses</h1>
    <h4>number of course added {{ count }}</h4>

    <CourseItem :courses="courses" @count-to-parent="addOne" />
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import CourseItem from "./components/CourseItem.vue";

export default {
  name: "App",
  data() {
    return {
      courses: [
        { id: 1, name: "react", location: "xyz" },
        { id: 2, name: "react js", location: "xyz" },
        { id: 3, name: "node js", location: "xyz" },
      ],
      count: 0,
    };
  },
  components: {
    // using the hello world component here
    // HelloWorld,
    CourseItem,
  },

  methods: {
    addOne() {
      this.count + -1;
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
