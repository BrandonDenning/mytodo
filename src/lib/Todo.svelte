<script lang="ts">
import { onMount } from "svelte";

let todos: string[] = [];
let newTodo: string = '';


onMount(() => {
    const storedTodos = localStorage.getItem('todos');
    if (storedTodos) {
        todos = JSON.parse(storedTodos);
    }
});

const addTodo = (todo) => {
  todos = [...todos, todo]
  newTodo = '';
  localStorage.setItem('todos', JSON.stringify(todos));
}

const removeTodo = (index) => {
    todos = todos.filter((_, i) => i !== index);
    localStorage.setItem('todos' , JSON.stringify(todos));
}

</script>


<form>
    <input type="text" bind:value={newTodo} placeholder="Add a new todo" />
    <button type="button" on:click={() => addTodo(newTodo)}>Add</button>
    <ul>
        {#each todos as todo, index}
            <li>
                {todo}
                <button type="button" on:click={() => 
                removeTodo(index)}>Remove</button>
            </li>
        {/each}
    </ul>
</form>