<template>
  <div id="app" class="small-container">
    <h1>Employees</h1>
    <employee-form @add:employee="addEmployee"></employee-form>
    <employee-table :employees="employees"></employee-table>
  </div>
</template>

<script>
import EmployeeForm from './components/EmployeeForm'
import EmployeeTable from './components/EmployeeTable.vue'

export default {
  name: 'app',
  components: {
    EmployeeForm,
    EmployeeTable,
  },
  data() {
    return{
    employees: [
      {
        id: 1,
        name: 'Kofi Ramos',
        email: 'kofiramos@example.com'
      },
      {
        id: 2,
        name: 'Kojo Ramos',
        email: 'kojoramos@example.com'
      },
    ],
  }
},
methods:{
  addEmployee(employee){
    const lastId =
    this.employees.length > 0 
    ? this.employees[this.employees.length - 1].id : 0;
    const id = lastId + 1;
    const newEmployee = {...employee, id};
    this.employees = [...this.employees, newEmployee];
  },
}
}
</script>

<style>
 button {
    background: #009435;
    border: 1px solid #009435;
  }

  .small-container {
    max-width: 680px;
  }
</style>
