<template>
  <div id="app">
    <input type="text" v-model="value" />
    <button @click.prevent="addTask">Add</button>
    <button @click.prevent="removeAll">Clear</button>
    <p v-for="(task, id) in tasks" :key="id">
      {{ task }}
      <button @click.prevent="removeItem(id)">REMOVE</button>
    </p>
  </div>
</template>
<script>
export default {
  name: "App",
  data() {
    return {
      tasks: [],
      value: "",
    };
  },
  methods: {
    addTask() {
      this.tasks.push(this.value);
    },
    removeItem(id) {
      this.tasks.splice(id, 1);
    },
    removeAll() {
      this.tasks = [];
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button {
  background: blue;
  padding: 5px;
  margin: 3px;
  color: white;
  border: 1px solid blue;
  border-radius: 5px;
}
</style>
