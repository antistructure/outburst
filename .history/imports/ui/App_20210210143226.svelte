<script>
  import { Meteor } from 'meteor/meteor';
  import { useTracker } from 'meteor/rdb:svelte-meteor-data';

  import PageLayout from './components/PageLayout.svelte';
  import Task from './components/Task.svelte';
import { Issues } from '../api/issues.js';
  
  function getTasks() {
    return [
      { _id: 1, text: "This is task 1" },
      { _id: 2, text: "This is task 2" },
      { _id: 3, text: "This is task 3" }
    ];
  }

  $: currentUser = useTracker(() => Meteor.user());
 
</script>

<PageLayout header hideHeader headerHeight={56} let:scroller>
  <div slot="header">
    <header class="header" class:shadow={!!scroller.scroll}>
			<h1 class="text-xl uppercase">Antistructure</h1>
		</header>
  </div>

  <div class="container">
    <ul class="text-xl text-red-500">
    {#each getTasks() as task}
      <Task
        key={task._id}
        task={task}
      />
    {/each}
    </ul>
  </div>
</PageLayout>
 
 
<div class="container text-center">
  <header>
    <h1 class="text-xl uppercase">Todo List</h1>
  </header>
  
</div>
