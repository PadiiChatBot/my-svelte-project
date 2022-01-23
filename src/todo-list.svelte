<style></style>

<script>
import { listTodos } from "./store";

let todos;

let todo_name;

const unsubscribe = listTodos.subscribe((value) => {
  todos = value;
});

const onAddTodo = () => {
  if (todo_name) {
    listTodos.set([todo_name, ...todos]);
    todo_name = "";
  }
};

const onRemoveClick = (index) => {
  // !!! not working  todos.splice(index, 1);

  const newTodos = [...todos];
  newTodos.splice(index, 1);

  listTodos.set(newTodos);
};
</script>

<section>
  <input bind:value="{todo_name}" />

  <button on:click="{onAddTodo}">add todo</button>

  <!-- key for each element in the array is not required:) -->

  {#each [...todos] as todo, index}
    <div>
      <p>{todo}</p>

      <button on:click="{() => onRemoveClick(index)}">Remove</button>
    </div>
  {/each}
</section>
