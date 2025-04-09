<script lang="ts">
import Todo from "$lib/Todo.svelte";


</script>


<title>MyTodo</title>
<meta name="description" content="A simple todo app built with SvelteKit and TypeScript." />


<h1>My ToDo List</h1>
<p>Make a ToDo List</p>


<Todo />



<style lang="css">
    h1 {
      color: #ff3e00;
      text-align: center;
    }
    p {
      font-size: 1.2em;
    }
    a {
      color: #00aaff;
      text-decoration: none;
    }
    a:hover {
      text-decoration: underline;
    }
  </style>