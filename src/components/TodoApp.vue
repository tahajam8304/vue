<template>
  <div class="container">
    <section>
      <input type="text" class="task" placeholder="ENTER YOUR TASK" v-model="InputTodo">
      <button @click="addTodo()" class="btn">ADD</button> 
 
    </section>
    <ul class="list-q" v-for="todo in todolist" :key="todo.id">
      <li class="list" v-if="todo!=''">
        {{ todo }}
      <button class="btn.danger" @click="() => deletetodo()">
        DELETE
      </button>
        
      </li>

    </ul>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  // props: {
  //   msg: String
  // }
data (){
  return{
    InputTodo:'',
    todolist: [''],
  }
},

methods:{
  addTodo() {
     this.todolist.push(this.InputTodo)
     this.InputTodo= ""
  },
   deletetodo(){
        const index = this.todolist.indexOf(this.InputTodo)
        if(index > -1){
          this.todolist.splice(1, index)
        }
   }
}
}

</script>


<style scoped>
ul {
  list-style-type: none;
}

</style>
