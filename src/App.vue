<template>
  <div class="container">
    <Header title="Track" />
    <Tasks @delete-task="deleteTask" :tasks='tasks' />
  </div>
</template>

<script>
import Header from './components/Header'
import Tasks from './components/Tasks'

export default {
  name: "App",
  components: {
    Header,
    Tasks
  },
  data() {
    return {
      tasks: [] 
    }
  },
  methods: {
    deleteTask(id) {
      console.log('task', id)
    }
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: 'Liverpool was created',
        day: 'march 1st march 1989 at 2:30pm',
        reminder: true
      },
      {
        id: 2,
        text: 'Barcelona was created',
        day: 'january 1st march 1989 at 1:30pm',
        reminder: true
      },
      {
        id: 3,
        text: 'Chelsea was created',
        day: 'march 1st march 1919 at 2:30pm',
        reminder: false
      },
    ]
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,600;0,700;1,400;1,500&display=swap');
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
body {
  font-family: "Poppins", sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
