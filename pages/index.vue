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
    <button @click="addTask">Add</button>
  </div>

  <div class="task">
    <Task
    v-for="(task,i) in $store.state.tasks"
    :key="i"
    :task="task"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: ''
    }
  },
  methods: {
    addTask() {
      if (this.newTask) {
        this.$store.commit('ADD_TASK', this.newTask);
        this.newTask= ''
      }
    }
  }
}
</script>
