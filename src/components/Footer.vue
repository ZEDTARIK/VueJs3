<template lang="">
    <div class="row">
        <div class="col-md-12">
            <div class="card text-center">
              <div class="card-body">
                <h4 class="card-title">{{title}}</h4>
                <p class="card-text">
                  {{ author }}
                </p>
              </div>
            </div>
        </div>
            
    </div>
</template>
<script>
export default {
    
    props: ['title', 'author']
}
</script>
<style lang="">
    
</style>