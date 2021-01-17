<template lang="">
    <div>
          <teleport to='#alert'>
            <div class="row">
            <div class="col-md-6 mx-auto" v-if="alertDeleted">
                <div class="alert alert-danger">
                <strong>Deleted SuccessFully !!</strong>
                </div>
            </div>

            <div class="col-md-6 mx-auto" v-if="alertAdd">
                <div class="alert alert-success">
                <strong>Add New Employee SuccessFully !!</strong>
                </div>
            </div>

            </div>
        </teleport>

        <div class="row" v-if="showForm">
            <div class="col-md-6 mx-auto">
                <AddEmployee @add="NewEmployee($event)">
                    <h3>Add New Employee</h3>
                </AddEmployee>
            </div>
        </div>

    <div class="row">
        <div class="col-md-6">
            <h3>List Employees</h3>
        </div>

        <div class="col-md-6 text-right">
            <button @click="displayForm" 
            class="btn"
            :class="{'btn-warning' : !showForm, 'btn-dark': showForm}">
            {{showForm ? 'Closed' :  'New'}}
        </button>
        </div>
    </div>

    <div class="row">
        <div class="col-md-4" v-for="employee in Employees" :key="employee.id">
            <DisplayEmployee 
                    :employee="employee" 
                    @delete="deletedEmployee($event)"  />
        </div>
    </div>

    </div>  
</template>
<script>
import AddEmployee from "./AddEmployee";
import DisplayEmployee from "./DisplayEmployee";

export default {
  data() {
    return {
      Employees: [
        {
          id: 1,
          fullName: "Zouhair ETTARAK",
          email: "ettarak@gmail.com",
        },
        {
          id: 2,
          fullName: "Lorem",
          email: "Lorem-5154@gmail.com",
        },
      ],
      showForm: false,
      alertDeleted: false,
      alertAdd: false,
    };
  },
  components: {
    AddEmployee,
    DisplayEmployee,
  },
  methods: {
    displayForm() {
      this.showForm = !this.showForm;
    },
    deletedEmployee(id) {
      this.Employees = this.Employees.filter((employee) => employee.id != id);
      this.alertDeleted = true;
      setTimeout(() => {
        this.alertDeleted = false;
      }, 4000);
    },
    NewEmployee(employee) {
      this.Employees = [employee, ...this.Employees];
      this.showForm = false;
      this.alertAdd = true;
      setTimeout(() => {
        this.alertAdd = false;
      }, 4000);
    },
  },
};
</script>
<style lang="">
</style>