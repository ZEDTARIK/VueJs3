<template lang="">
  
     <div class="card">
       <div class="card-body">
        
            <slot>No content</slot>
        
        <form @submit.prevent="newCourse()">
          
          <div class="form-group">
          <label for="Title">Title</label>
          <input v-model="title" id="Title" class="form-control" type="text" />
        </div>

        <div class="form-group">
          <label for="Image">Image</label>
          <input v-model="image" id="Image" class="form-control" type="text" />
        </div>

        <div class="form-group">
          <label for="category">Category</label>
          <select class="form-control"  id="category" v-model="category">
            <option  v-for="Mycategory in categories" 
                    :key="Mycategory.id" 
                    :value="Mycategory.id">
                    
                  {{ Mycategory.description}}
            </option>
          </select>
        </div>
        

        <div class="form-check form-check-inline">
          <label class="form-check-label">
            <input class="form-check-input" type="radio" v-model="methodPayment" value="Free"> 
            Free
          </label>
          <label class="form-check-label ml-3">
            <input class="form-check-input" type="radio" v-model="methodPayment" value="Payment"> 
            Payment
          </label>
        </div>

     <div>
       <label>Tags : </label>
          <div class="form-check form-check" v-for="myTag in tags" :key="myTag.index">
          
          <label class="form-check-label" > 
            <input class="form-check-input" type="checkbox" 
                    v-model="tag"
                    :value="myTag">  
                    {{ myTag }}
          </label>
        </div>
     </div>

          <button class="btn btn-warning btn-block"> Add Course </button>

        </form>

       </div>
     </div>

</template>
<script>
export default {
  data() {
    return {
      title:'',
      image:'',
      category:'',
      categories : [
        { id:1, description: 'FrontEnd'},
        { id:2, description: 'BackEnd'},
        { id:3, description: 'FullStack'},
        { id:4, description: 'Mobile'}
      ],
      tags : ['Freamwork', 'Back End', 'Front End', 'Language Pure'],
      tag: [],
      published:false,
      methodPayment: 'Free'
    }
  },
    methods:{
      newCourse(){
        let id = Math.floor(Math.random(100)* 51);
        let title = this.title;
        let image = this.image;
        let published = this.published;
      
        const course = {
          id,
          title,
          image,
          category : this.categories.find(cat => cat.id  == this.category).description,
          published,
          tags : this.tag
        }

        this.$emit('add',course);
        this.title = "";
        this.image = "";
      }
    }
}
</script>
<style lang="">
    
</style>