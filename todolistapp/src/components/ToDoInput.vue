<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" @keyup.enter="addTodo"/>
    <!-- <button @click="addTodo">add</button> -->
    <span class="addContainer" @click="addTodo">
      <i class="fas fa-plus addBtn"></i>
    </span>
  </div>
</template>

<script>
export default {
  data () {
    return {
      newTodoItem: ''
    }
  },
  methods: {
    addTodo () {
      console.log(this.newTodoItem)
      // 여기서 this는 해당 컴포넌트의 data
      // 저장하는 로직
      localStorage.setItem(this.newTodoItem, this.newTodoItem)
      this.clearInput()
    },
    clearInput () {
      this.newTodoItem = ''
    }
  }
}
</script>

<style scopedd>
input:focus {
  outline: none;
}
.inputBox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}
.inputBox input {
  border-style: none;
  font-size: 0.9rem;
}
.addContainer {
  float : right;
  background: linear-gradient(to right, #6478FB, #8763FB);
  display: block;
  width: 3rem;
  border-radius: 0 5px 5px 0;
}
.addBtn {
  color:white;
  vertical-align: middle;
}
</style>
