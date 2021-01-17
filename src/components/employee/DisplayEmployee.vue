<template lang="">
    <div class="my-3">
    
        <div class="card" style="width: 18rem;">
            <div class="card-header text-center">
                {{employee.fullName }}
            </div>
            <ul class="list-group list-group-flush">
                <li class="list-group-item">{{employee.email}}</li>
                <li class="list-group-item">
                    <button  type="button" 
                            @click="onDelete(employee.id)" 
                             class="btn btn-danger btn-sm">
                            Delete
                    </button>
                </li>
            </ul>
        </div>

    </div>
</template>
<script>
export default {
  props: ["employee"],
  data() {
    return {};
  },
  methods: {
      onDelete(id) {
          this.$emit('delete', id)
      }
  }
};
</script>
<style scoped>
</style>