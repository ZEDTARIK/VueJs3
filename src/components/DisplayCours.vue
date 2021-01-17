<template lang="">
      <div class="card my-3">
            <img class="card-img-top" :src="course.image" :alt="course.title">
            <div class="card-body">
                <h4 class="card-title"> {{ course.title }} </h4>
                <p class="card-text">
                    Lorem ipsum dolor sit amet consectetur.
                </p>
                <button class="btn btn-danger" @click="onDelete(course.id)">Delete</button>
                <button class="btn btn-dark ml-3">
                    {{course.category}}
                </button>

                <div>
                  <span v-for="tag in course.tags" :key="tag" class="badge badge-pill badge-primary ml-3" >
                      {{tag}}
                  </span>
                </div>

            </div>
        </div>
</template>
<script>
export default {
  props: ["course"],
  methods: {
    onDelete(id) {
      this.$emit("emitDeleteCourse", id);
    },
  },
};
</script>
<style lang="">
</style>