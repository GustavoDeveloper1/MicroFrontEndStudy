<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <form @submit.prevent="add()">
      <input v-model="task" type="text"  />
      <button type="submit">ENVIAR</button>
    </form>

    <ul>
      <li v-for="t in tasks" :key="t">{{t}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "helloworld",
  props: {
    msg: String,
  },
  data() {
    return {
      task: "",
      tasks: [],
    };
  },
  methods: {
    add() {
      if(this.task.trim()) {
        this.tasks.push(this.task);
        this.task = '';
      }
    }
  }
};
</script>
