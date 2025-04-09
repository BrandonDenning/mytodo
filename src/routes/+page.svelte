<script lang="ts">
import Todo from "$lib/Todo.svelte";


</script>


<title>MyTodo</title>
<meta name="description" content="A simple todo app built with SvelteKit and TypeScript." />


<h1>My ToDo List</h1>



<Todo />



<style lang="css">
    h1 {
      color: #00aaff;
      text-align: center;
      font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
      text-shadow: 2px 2px 5px #071679
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