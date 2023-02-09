<template>
  <div>
    <h1>Minha lista de tarefas</h1>
    <input type="text" placeholder="insira nova tarefa" v-focus="focus" v-model="currentTask" @keyup.enter="addTask">
    <ul>
      <li 
        v-for="task, index in tasks"
        :key="`${index}`"
        @dblclick="finishTask"
      >
        {{ task }}
      </li>
    </ul>
  </div>
</template>

<script>
const focus = {
    inserted: (el) => {
      el.focus()
    }
}
export default {
  directives: {
    focus,
  },
  data: () => {
    return {
      currentTask: '',
      tasks: [],
      focus
    }
  },
  methods: {
    finishTask(e) {
      e.target.classList.toggle('finished')
    },
    addTask() {
      this.tasks.push(this.currentTask)
      this.currentTask = ''
    },
  }
}
</script>

<style>
  .finished {
    text-decoration: line-through solid black;
  }
</style>