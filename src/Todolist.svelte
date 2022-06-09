<script>
  import { todolist } from "./store";
  import { validateString, initData } from "./utils";
  let todo = "";
  let list = [];

  function handleKeypress({ key }) {
    key === "Enter" && addTodo();
  }

  function addTodo() {
    if (validateString(todo) === false) {
      todo = initData();
    } else {
      list.push(todo);
      $todolist = list;
      todo = initData();
    }
  }
</script>

<main>
  <input
    type="text"
    placeholder="write here"
    on:change={(e) => (todo = e.target.value)}
    bind:value={todo}
    on:keypress={(e) => handleKeypress(e)}
  />
  <button on:click={addTodo}>ADD TODO</button>
</main>
