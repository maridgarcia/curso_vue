<template>
  <div>
    <h1>Minha lista de tarefas</h1>
    <input type="text" placeholder="insira nova tarefa" v-focus="focus">
    <ul>
      <li 
        v-for="task, index in tasks"
        :key="`${index}`"
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
  data: () => {
    return {
      tasks: [{ name:'Fazer curso', isDone: false }],
      focus
    }
  },
  methods: {
    remove(task) {
      this.tasks = this.tasks.filter((t) => t.name !== task.name)
    }
  }
}
</script>
