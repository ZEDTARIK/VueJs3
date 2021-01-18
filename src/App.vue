<template>

  <div class="container">
    <div class="row">
      <div class="col-md-12">
        <Header />
      </div>
    </div>
    <div class="row">
      <div class="col-md-6 mx-auto text-center">
        <h1>{{ message }}</h1>
      </div>
    </div>
    <Books />
    <Footer title="Pass Data From Parent to Child Using Props" author="Zouhair ETTARAK" />
  </div>
</template>

<script>
import Header from "./components/Header";
import Books from "./components/book/Books"
import Footer from "./components/Footer"


export default {
  name: "App",
  components: {
    Header,
    Books,
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
