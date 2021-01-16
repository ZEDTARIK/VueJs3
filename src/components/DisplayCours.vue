<template lang="">
      <div class="card my-3">
            <img class="card-img-top" :src="image" :alt="title">
            <div class="card-body">
                <h4 class="card-title"> {{ title }} </h4>
                <p class="card-text">
                    Lorem ipsum dolor sit amet consectetur.
                </p>
            </div>
        </div>
</template>
<script>
export default {
    props : ['title', 'image']
}
</script>
<style lang="">
    
</style>