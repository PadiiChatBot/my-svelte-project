<style>
.todo {
  display: flex;
  justify-content: center;
}

.todoName {
  margin-right: 5px;
}
</style>

<script>
import { listTodos } from "./store";

let todos;

let todoName = "";

const unsubscribe = listTodos.subscribe((value) => {
  todos = value;
});

const onAddTodo = () => {
  if (todoName) {
    listTodos.set([todoName.trim(), ...todos]);
    todoName = "";
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
  <input bind:value="{todoName}" />

  <button disabled="{!todoName.trim()}" on:click="{onAddTodo}">add todo</button>

  <!-- key for each element in the array is not required:) -->

  {#each todos as todo, index}
    <div class="todo">
      <p class="todoName">{todo}</p>

      <button on:click="{() => onRemoveClick(index)}">Remove</button>
    </div>
  {/each}
</section>
