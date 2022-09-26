<template>
  <main>
    <h1>Task board</h1>
    <p>Create a list of task</p>
  </main>

  <div class="create-new">
    <input 
    type="text" 
    v-model="newTask" 
    placeholder="Add a new task" 
    @keypress.enter="addTask">
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>
