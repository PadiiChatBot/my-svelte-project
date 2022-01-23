<script>
    import {listTodos} from "./store";

    let todos;

    let todo_name;

    const unsubscribe = listTodos.subscribe(value => {
        todos = value
    })


    const onAddTodo = ()=>{
        if(todo_name){
            listTodos.set([todo_name,...todos])
            todo_name='';
        }
    }
</script>

<section>
    <hr>
    <input bind:value={todo_name}/>

    <button on:click={onAddTodo}>add todo</button>

    {#each [...todos] as todo}
        <p>{todo}</p>
    {/each}
</section>

<style></style>