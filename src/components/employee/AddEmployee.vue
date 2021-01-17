<template lang="">
    <div class="my-2">
        
        <div class="card">
            <div class="card-body">
                    <div class="card-header">
                        <slot></slot>
                    </div>


                <form @submit.prevent="addEmployee()">
                    <div class="form-group">
                      <label for="fullName">FullName</label>
                      <input type="text"
                        class="form-control" id="fullName" 
                        v-model="fullName" placeholder="FullName">
                    </div>
        
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="text"
                          class="form-control" id="email" 
                          v-model="email"  placeholder="Email">
                      </div>
        
                    <button type="submit" class="btn btn-warning btn-block">Submit</button>

                </form>
        
            </div>
        </div>
    </div>
</template>
<script>
export default {
  data() {
    return {
      fullName: "",
      email: "",
    };
  },
  methods: {
      addEmployee() {
    let fullName = this.fullName;
    let email = this.email;
    const employee = {
      id: Math.floor(Math.random(10) * 523),
      fullName,
      email,
    };

    this.$emit("add", employee);
  }
  }
};
</script>
<style lang="">
</style>