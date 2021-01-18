<template>
  <div>
    <teleport to="#alert">
      <div class="row my-3">
        <div class="col-md-6 mx-auto">
          <div class="alert alert-danger" v-if="alertDelete">
            Book is Deleted
          </div>

          <div class="alert alert-success" v-if="alertAdd">
            Book Add with SuccessFully
          </div>
        </div>
      </div>
    </teleport>

    <div class="row" v-if="showForm">
      <div class="col-md-6 mx-auto">
        <AddBook @add="addBook($event)" />
      </div>
    </div>

    <div class="row">
      <div class="col-md-6">
        <h3>List of Books</h3>
      </div>
      <div class="col-md-6 text-right">
        <button
          type="button"
          class="btn btn-sm"
          :class="{ 'btn-warning': !showForm, 'btn-dark': showForm }"
          @click="DisplayForm()"
        >
          {{ showForm ? "Closed" : "New Book" }}
        </button>
      </div>
    </div>
    <div class="row">
      <div class="col-md-4" v-for="book in Books" :key="book.id">
        <DisplayBook :book="book" @delete="deleteBook($event)" />
      </div>
    </div>
  </div>
</template>

<script>
import DisplayBook from "./DisplayBook";
import AddBook from "./AddBook";

export default {
  data() {
    return {
      showForm: false,
      alertDelete: false,
      alertAdd: false,
      Books: [
        {
          id: 1,
          author: "Zouhair ETTARAK",
          title: "Spring Book",
          image:
            "https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/5miGPBu8RbCSc4hCzN39",
        },
        {
          id: 2,
          author: "Elgatek TEAM",
          title: ".NET && Freamwork Laravel",
          image:
            "https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/aL2OXWSpTguVo0azLaPb",
        },
        {
          id: 2,
          author: "FORWORK",
          title: "JAVA SCRIPT",
          image:
            "https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/H9QyEOsSLG05qNb2kC0V",
        },
      ],
    };
  },
  components: {
    DisplayBook,
    AddBook,
  },
  methods: {
    deleteBook(id) {
      this.Books = this.Books.filter((book) => book.id != id);
      this.alertDelete = true;
      setTimeout(() => {
        this.alertDelete = false;
      }, 3000);
    },
    DisplayForm() {
      this.showForm = !this.showForm;
    },
    addBook(book) {
      this.Books = [book, ...this.Books];
      this.showForm = false;
      this.alertAdd = true;
      setTimeout(() => {
        this.alertAdd = false;
      }, 3000);
    },
  },
};
</script>

<style scoped>
h3 {
  color: goldenrod;
}
</style>