<template>
  <div>
    <form v-on:submit.prevent="addTask">
      <input
        v-model="newTask"
        class="px-3"
        type="text"
        placeholder="Tambah task baru"
      />
      <button type="submit">Tambah</button>
    </form>

    <ul>
      <li v-for="(task, index) in tasks" :key="index">{{ task }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: '',
      tasks: [],
    }
  },
  methods: {
    addTask() {
      if (this.newTask.trim() !== '') {
        this.tasks.push(this.newTask)
        this.newTask = ''
      }
    },
  },
}
</script>
