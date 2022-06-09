<script>
  import { todolist } from "./store";
  let todo = "";
  let list = [];

  function handleKeypress({ key }) {
    key === "Enter" && addTodo();
  }

  function addTodo() {
    list.push(todo);
    $todolist = list;
    todo = "";
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
  <button on:click={addTodo}>ADD</button>
</main>
