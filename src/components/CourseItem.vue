<template>
  <div v-for="course in courses" :key="course.id">
    <h2>name: {{ course.name }}</h2>
    <p>location: {{ course.location }}</p>
    <!-- <p>{{ courses }}</p> -->

    <button v-if="!course.added" @click="innerAdd">Add</button>
    <button @click="outerAdd">Add to course list</button>
  </div>
</template>

<script>
export default {
  name: "CourseItem",

  data() {
    return {
      //   title: "Title:course one",
      //   location: "location: xyz",
      //   description:
      //     "description: utomatically inherited because component renders",
      count: 0,

      courses: [
        { id: 1, name: "react", location: "xyz", },
        { id: 2, name: "react js", location: "xyz"  },
        { id: 3, name: "node js", location: "xyz" },
      ],
    };
  },
  methods: {
    innerAdd() {
      this.count += 1;
    },

    outerAdd() {
      this.$emit("count-to-parent");
    },
  },
};
</script>
