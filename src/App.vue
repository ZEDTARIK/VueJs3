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
    <Footer title="Pass Data From Parent to Child Using Props" author="Zouhair ETTARAK" />
  </div>
</template>

<script>
import Header from "./components/Header";
import AddCourse from "./components/AddCourse";
import Courses from "./components/Courses"
import Footer from "./components/Footer"


export default {
  name: "App",
  components: {
    Header,
    AddCourse,
    Courses,
    Footer
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
