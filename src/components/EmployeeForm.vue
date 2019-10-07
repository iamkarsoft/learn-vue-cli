<template>
<div id="employee-form">
  <form action="" @submit.prevent="handleSubmit" class="">
    <label for="">Employee name</label>
    <input type="text" v-model="employee.name" id="">
    <label for="">Employee email</label>
    <input type="text" v-model="employee.email" name="" id="">
    <button>Add Employee</button>

  </form>

</div>
</template>

<script>
export default {
  name: 'employee-form',
  data(){
    return{
      employee:{
        name:'',
        email:'',
      }
    }
  },
  methods: {
    handleSubmit(){
      this.$emit('add:employee', this.employee)
    }
  }
}
</script>

<style scoped>
form{
  margin-bottom: 2rem;
}
</style>