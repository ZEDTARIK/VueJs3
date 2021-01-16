<template lang="">
    
   <div class="row">
    <div class="col-md-4"  v-for="course in Courses" :key="course.id">
        <div class="card my-3">
            <img class="card-img-top" :src="course.image" :alt="course.title">
            <div class="card-body">
                <h4 class="card-title"> {{ course.title}} </h4>
                <p class="card-text">
                    Lorem ipsum dolor sit amet consectetur.
                </p>
            </div>
        </div>
    </div>
   </div>

</template>
<script>
export default {
    
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
<style lang="">
    
</style>