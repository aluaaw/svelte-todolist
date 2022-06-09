<script>
  export let name;
  import Todolist from "./Todolist.svelte";
  import { todolist } from "./store";
</script>

<main>
  <h3>List : {name}</h3>
  <h4>Add Your Todo</h4>
  <Todolist />

  <h4>Your List</h4>
  {#each $todolist as todo, i}
    <div>
      <input type="checkbox" />
      {i + 1}. {todo}
    </div>
  {/each}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h3 {
    color: green;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
