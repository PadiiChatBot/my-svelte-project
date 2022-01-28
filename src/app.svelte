<style>
header {
  display: flex;
  justify-content: center;
}

main {
  text-align: center;
  padding: 1em;
  max-width: 240px;
  margin: 0 auto;
}

h1 {
  color: #ff3e00;
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

<script>
import Form from "./form.svelte";
import Counter from "./counter.svelte";
import TodoList from "./todo-list.svelte";
import Animation from "./animations.svelte";
import { Router, Route, Link } from "svelte-navigator";
import { afterUpdate, beforeUpdate, onDestroy, onMount } from "svelte";

onDestroy(() => {});

beforeUpdate(() => {});

afterUpdate(() => {});

onMount(async () => {});
export let name = "default value";
</script>

<Router>
  <header>
    <nav>
      <Link to="/">Counter</Link>

      <Link to="form">Form</Link>

      <Link to="todos">Todo List</Link>

      <Link to="animation">Animation</Link>
    </nav>
  </header>

  <main>
    <hr />
    <h1>Props: {name}!</h1>

    <Route path="form">
      <Form />
    </Route>

    <Route path="todos">
      <TodoList />
    </Route>

    <Route path="animation">
      <Animation />
    </Route>

    <Route path="/">
      <Counter counter="{4}" />
    </Route>
  </main>
</Router>
