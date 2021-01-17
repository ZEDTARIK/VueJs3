<template lang="">

  <div class="row" v-if="showForm">
    <div class="col-md-6 mx-auto">
      <AddCourse @add="addCourse($event)">
        <label> add New Cours <i>using Slot Injection</i></label>
      </AddCourse>
    </div>
  </div>

  <div class="row my-3">
    <div class="col-md-6">
      <h1> List of Courses </h1>
    </div>

    <div class="col-md-6 text-right">
      <button @click="displayForm" class="btn btn-sm" :class="{'btn-success' : !showForm, 'btn-dark': showForm}">
        {{ showForm ? 'Close' : 'New Course' }}
      </button>
    </div>

  </div>

  <div class="row">
    <div class="col-md-4" v-for="course in Courses" :key="course.id">

      <DisplayCours :id="course.id" :title="course.title" :image="course.image"
        @emitDeleteCourse="deleteOneCourse($event)" />

    </div>
  </div>

</template>
<script>
  import DisplayCours from "./DisplayCours";
  import AddCourse from './AddCourse';

  export default {
    components: {
      AddCourse,
      DisplayCours
    },
    data() {
      return {
        showForm: false,
        Courses: [
          {
            id: 1,
            title: "Learn Angular",
            image:
              "https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/nrOHB2iQTIiGe7hHX9O0",
          },
          {
            id: 2,
            title: "Learn NodeJs",
            image:
              "https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/yMO0mZjvTm2pwyeOQUpT",
          },
          {
            id: 3,
            title: "Learn ReactJs",
            image:
              "https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/C2oT8I1eTXGg69ytJ69f",
          },
        ],
      };
    },
    methods: {
      deleteOneCourse(id) {
        this.Courses = this.Courses.filter((course) => course.id != id);
      },
      addCourse(course) {
        this.Courses = [course, ...this.Courses],
          this.showForm = false;
      },
      displayForm() {
        this.showForm = !this.showForm
      }
    },
  };
</script>
<style scoped>
  h1 {
    color: brown;
  }
</style>