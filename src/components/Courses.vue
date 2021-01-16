<template lang="">
    
    <div class="row">
        <div class="col-md-12">
            <h1>
                List of Courses
            </h1>
        </div>
    </div>

   <div class="row">
    <div class="col-md-4"  v-for="course in Courses" :key="course.id">
        
        <DisplayCours :title="course.title" :image="course.image" />
        
    </div>
   </div>

</template>
<script>

import DisplayCours from './DisplayCours'

export default {

    components: {
        DisplayCours
    },
    data() {
        return {
            Courses : [
                {
                    id:1,
                    title:'Learn Angular',
                    image:'https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/nrOHB2iQTIiGe7hHX9O0'
                },
                {
                    id:2,
                    title:'Learn NodeJs',
                    image:'https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/yMO0mZjvTm2pwyeOQUpT'
                },
                {
                    id:3,
                    title: 'Learn ReactJs',
                    image:'https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/C2oT8I1eTXGg69ytJ69f'
                }
            ]
        }
    }
}
</script>
<style scoped>
    h1 {
        color: brown;
    }
</style>