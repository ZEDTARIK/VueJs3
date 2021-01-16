<template>

<Header />

  <div class="container">
    <div class="row mt-5">
      <div class="col-md-6 mx-auto">
        <h1>{{ message }}</h1>
        <AddCourse />
      </div>
    </div>
    <Courses />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import AddCourse from "./components/AddCourse.vue";
import Courses from "./components/Courses.vue"

export default {
  name: "App",
  components: {
    Header,
    AddCourse,
    Courses
  },
  data() {
    return {
      message: "Formation VueJs 3",
    };
  },
  methods: {
    handlClick() {
      this.$refs.book.classList.add("active");
    },
  },
};
</script>

<style>
.container{
  margin-top: 60px;
}
</style>
