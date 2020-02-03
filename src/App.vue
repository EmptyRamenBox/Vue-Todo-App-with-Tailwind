<template>
   <div
      class="h-screen w-widht bg-blue-600 flex flex-col justify-center items-center shadow-2xl"
    >
      <div class="header text-white font-bold">
        <h1 class="text-4xl">To-Do App with Tailwind</h1>
        <div class="form flex">
          <input
            v-model="newTodo"
            @keyup="checkAdd"
            class="appearance-none border w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none"
            id="newText"
            type="text"
            placeholder="Add new Todo"
          />
          <button
            id="newBtn"
            @click="add"
            class="bg-blue-800 hover:bg-green-600 text-white font-bold py-2 px-4"
          >
            Add
          </button>
        </div>
      </div>
      <div class="todos w-1/2 mt-8 font-bold">
        <div class="pendings" v-if="totalPendings>0">
          <h3 class="text-2xl text-white">Pendings  -  {{totalPendings}}:</h3>
          <ul id="pendingList">
            <li
            @click="moveToCompleted(pending)"
            v-for="(pending, index) in pendingsList"
            :key="index" 
            class="text-center p-3 bg-yellow-500 mt-4 rounded shadow-lg cursor-pointer hover:bg-blue-800 hover:text-green-200">{{pending}}</li>

          </ul>
        </div>
        <div class="completed mt-8 text-white" v-if="totalCompleted>0">
          <h3 class="text-2xl">Completed  -  {{totalCompleted}}:</h3>
          <ul id="completedList">
            <li 
            v-for="(completed, index) in completedList"
            :key="index"
            @click="moveToPending(completed)"
            class="text-center p-3 bg-orange-600 line-through text-red-900 mt-4 rounded shadow-lg cursor-pointer hover:bg-blue-800 hover:text-red-300">{{completed}}</li>

          </ul>
        </div>
      </div>
    </div>
</template>

<script>

export default {
  name: 'app',
  data() {
    return {
      newTodo: "",
      pendingsList: [],
      completedList: []
    };
  },
  computed: {
    totalPendings() {
      return this.pendingsList.length;
    },
    totalCompleted() {
      return this.completedList.length;
    }
  },
  methods: {
    add() {
      if (this.newTodo!="") {
        this.pendingsList.push(this.newTodo);
        this.newTodo = "";
      } else {
        alert('Please specify the task to Add')
      }
    },
    checkAdd(event) {
      if (event.keyCode === 13) {
        event.preventDefault();
        this.add();
      }
    },
    moveToCompleted(todo, index) {
      this.completedList.push(todo);
      this.pendingsList.splice(index, 1);
    },
    moveToPending(todo, index) {
      this.pendingsList.push(todo);
      this.completedList.splice(index, 1);
    }
  }
}
</script>

