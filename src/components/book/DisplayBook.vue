<template>
  <div>
    <div class="card my-3">
      <img class="card-img-top" :src="book.image" :alt="book.title" />
      <div class="card-body">
        <h4 class="card-title text-center">{{ book.author }}</h4>
        <p class="card-text text-center">
          {{ book.title }}
        </p>
        <p>
          <button
            type="button"
            class="btn btn-sm btn-danger"
            @click="onDelete(book.id)"
          >
            Delete
          </button>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["book"],
  data() {
    return {};
  },
  methods: {
    onDelete(id) {
      this.$emit("delete", id);
    },
  },
};
</script>

<style>
</style>