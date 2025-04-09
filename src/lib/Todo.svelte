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


<style>
    form {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-top: 20px;
    }
  
    input[type="text"] {
      padding: 10px;
      font-size: 16px;
      margin-bottom: 10px;
      border: 1px solid #ccc;
      border-radius: 4px;
      width: 80%;
    }
  
    button {
      padding: 10px 20px;
      font-size: 16px;
      color: white;
      background-color: #007BFF;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
  
    button:hover {
      background-color: #0056b3;
    }
  
    ul {
      list-style-type: none;
      padding: 0;
      width: 80%;
    }
  
    li {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 4px;
      margin-bottom: 5px;
      background-color: #f9f9f9;
    }
  
    li button {
      background-color: #dc3545;
    }
  
    li button:hover {
      background-color: #c82333;
    }
  </style>