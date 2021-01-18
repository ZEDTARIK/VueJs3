<template>
  <div>
    <div class="card">
      <div class="card-body">
        <h5 class="card-title text-center">Add New Book</h5>
        <div class="card-text">
          <form class="form-horizontal" @submit.prevent="onSubmit()">
            <div class="form-group">
              <label for="Author">Author</label>
              <input
                type="text"
                id="Author"
                class="form-control"
                placeholder="Author"
                v-model="author"
              />
            </div>

            <div class="form-group">
              <label for="title">Title</label>
              <input
                type="text"
                id="title"
                class="form-control"
                placeholder="Title"
                v-model="title"
              />
            </div>

            <div class="form-group">
              <label for="image">Image Book</label>
              <input
                type="text"
                id="image"
                class="form-control"
                placeholder="image"
                v-model="image"
              />
            </div>

            <button class="btn btn-warning btn-sm btn-block">Save</button>

          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      author: "",
      title: "",
      image: "",
    };
  },
  components: {},
  methods: {
    onSubmit() {
      const book = {
        id: Math.floor(Math.random(5) * 94),
        author: this.author,
        title: this.title,
        image: this.image,
      };

      this.$emit("add", book);
    },
  },
};
</script>

<style>
h5 {
  color: goldenrod;
}
</style>