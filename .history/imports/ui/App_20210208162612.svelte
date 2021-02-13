<script>
  import Task from './components/Task.svelte';
  
  function getTasks() {
      return [
        { _id: 1, text: "This is task 1" },
        { _id: 2, text: "This is task 2" },
        { _id: 3, text: "This is task 3" }
      ];
    }
 
</script>
 
 
<div class="container text-center">
  <header>
    <h1 class="text-xl uppercase">Todo List</h1>
  </header>
  <ul class="text-xl text-red-500">
  {#each getTasks() as task}
    <Task
      key={task._id}
      task={task}
    />
  {/each}
  </ul>
</div>
