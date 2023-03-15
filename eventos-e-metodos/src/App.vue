<template>
  <div>
    <h1>Minha lista de tarefas</h1>
    <input
      type="text"
      placeholder="insira nova tarefa"
      v-focus
      v-model="currentTask"
      @keyup.enter="add">
    <ul>
      <li 
        v-for="task, index in tasks"
        :key="`${index}`"
        @dblclick="complete(task)"
        class="task-item"
        :class="{
          'completed': task.isDone
        }"
      >
        {{ task.name }}
        <button
          @click="remove(task)"
        >&times;</button>
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
  mounted () {
    console.log("foi montado")
  },
  data: () => {
    return {
      currentTask: '',
      tasks: [{ name:'Fazer curso', isDone: false }],
      focus
    }
  },
  methods: {
    add() {
      this.tasks.push({
        name: this.currentTask,
        isDone: false
      })
      this.currentTask = ''
    },
    remove(task) {
      this.tasks = this.tasks.filter((t) => t.name !== task.name)
    },
    complete(task) {
      this.tasks = this.tasks.map(t => {
        if (t.name === task.name) {
          return {...t, isDone: !t.isDone}
        }
        return {...t}
      })
    },
  }
}
</script>

<style>
  .completed {
    text-decoration: line-through;
  }

  .task-item {
    cursor: pointer;
  }
</style>