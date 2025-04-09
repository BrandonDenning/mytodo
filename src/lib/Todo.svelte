<script lang="ts">

let todos: string[] = [];
let newTodo: string = '';


const addTodo = (todo) => {
  todos = [...todos, todo]
}
</script>


<form>
    <input type="text" bind:value={newTodo} placeholder="Add a new todo" />
    <button type="button" on:click={() => addTodo(newTodo)}>Add</button>
    <ul>
        {#each todos as todo}
            <li>{todo}</li>
        {/each}
    </ul>
</form>