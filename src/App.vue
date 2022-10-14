<template>
  <main>
    <div class="container">
      <h1>欢迎使用HYH待办事项!</h1>
      <div class="input-add">
        <input type="text" name="todo">
        <button>
          <i class="plus"></i>
        </button>
      </div>
      <div class="filters">
        <span class="filter active"></span>
        <span class="filter"></span>
        <span class="filter"></span>
      </div>
      <div class="todo-list">
        <div class="todo-item">
          <label for="">
            <input type="checkbox">
            Todo1
            <span class="check-button"></span>
          </label>
        </div>
        <div class="todo-item">
          <label for="">
            <input type="checkbox">
            Todo2
            <span class="check-button"></span>
          </label>
        </div>
        <div class="todo-item">
          <label for="">
            <input type="checkbox">
            Todo3
            <span class="check-button"></span>
          </label>
        </div>

      </div>
    </div>
  </main>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Helvetica, sans-serif;
}

/* all of page */
main {
  width: 100vw;
  min-height: 100vh;
  display: grid;
  align-items: center;
  justify-content: center;
  background-color: rgb(203, 210, 240);
}

.container {
  width: 60%;
  max-width: 400px;
  box-shadow: 0 0 24px rgba(0, 0, 0, 0.15);
  border-radius: 24px;
  padding: 48px 28px;
  background-color: rgb(245, 246, 252);
}

/* title */
h1 {
  margin: 24px 0;
  font-size: 28px;
  color: #414873;
}
</style>
