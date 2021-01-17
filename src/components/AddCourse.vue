<template lang="">
  
     <div class="card">
       <div class="card-body">
        
            <slot>No content</slot>
        
        <div class="form-group">
          <label for="Title">Title</label>
          <input ref="title" id="Title" class="form-control" type="text" />
        </div>

        <div class="form-group">
          <label for="Image">Image</label>
          <input ref="image" id="Image" class="form-control" type="text" />
        </div>
          
        <button @click="newCourse" class="btn btn-warning btn-block">
          Add Course
        </button>
       </div>
     </div>

    
</template>
<script>
export default {
    methods:{
      newCourse(){
        let id = Math.floor(Math.random(100)* 51);
        let title = this.$refs.title.value;
        let image = this.$refs.image.value;

        const course = {
          id,
          title,
          image
        }

        this.$emit('add',course);
        this.$refs.title.value = "";
        this.$refs.image.value = "";
      }
    }
}
</script>
<style lang="">
    
</style>