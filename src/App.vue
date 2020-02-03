<template>
   <div
      class="h-screen w-widht bg-blue-600 flex flex-col justify-center items-center shadow-2xl"
    >
      <div class="header text-white font-bold">
        <h1 class="text-4xl">To-Do App with Tailwind</h1>
        <div class="form flex">
          <input
            class="appearance-none border w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none"
            id="newText"
            type="text"
            placeholder="Add new Todo"
          />
          <button
            id="newBtn"
            class="bg-blue-800 hover:bg-green-600 text-white font-bold py-2 px-4"
          >
            Add
          </button>
        </div>
      </div>
      <div class="todos w-1/2 mt-8 font-bold">
        <div class="pendings ">
          <h3 class="text-2xl text-white">Pendings:</h3>
          <ul id="pendingList">
            <li class="text-center p-3 bg-yellow-500 mt-4 rounded shadow-lg cursor-pointer hover:bg-blue-700 hover:text-green-200">Item 1</li>
            <li class="text-center p-3 bg-yellow-500 mt-4 rounded shadow-lg cursor-pointer hover:bg-blue-700 hover:text-green-200">Item 2</li>
          </ul>
        </div>
        <div class="completed mt-8 text-white">
          <h3 class="text-2xl">Completed:</h3>
          <ul id="completedList">
            <li class="text-center p-3 bg-orange-500 line-through text-red-900 mt-4 rounded shadow-lg cursor-pointer hover:bg-blue-800 hover:text-red-300">Item 3</li>
            <li class="text-center p-3 bg-orange-500 line-through text-red-900 mt-4 rounded shadow-lg cursor-pointer hover:bg-blue-800 hover:text-red-300">Item 4</li>
          </ul>
        </div>
      </div>
    </div>
</template>

<script>

export default {
  name: 'app'
}
</script>

