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
import { Router, Route, Link } from "svelte-navigator";

export let name = "default value";
</script>

<Router>
  <header>
    <nav>
      <Link to="/">Counter</Link>

      <Link to="form">Form</Link>

      <Link to="todos">Todo List</Link>
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

    <Route path="/">
      <Counter counter="{1}" />
    </Route>
  </main>
</Router>
