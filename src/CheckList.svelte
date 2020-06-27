<script type="text/javascript">
export let tasks;
</script>

<div class="checklist">
  <ul>
    {#each tasks as task (task.id)}
    <li class="task">
      <input type="checkbox" bind:checked={task.done} />
      {task.name}
      <a href="#" class="remove" />
    </li>
    {/each}
  </ul>
  <input type="text" class="add-task" placeholder="Type then hit Enter to add a task" />
</div>

<style>
.task:first-child {
  margin-top: 10px;
  padding-top: 10px;
  border-top: dashed 1px #ddd;
}
.remove:after {
  display: inline-block;
  color: #d66;
  content: '+'
}
.add-task {
  border: 1px dashed #bbb;
  width: 100%;
  padding: 10px;
  margin-top: 5px;
  border-radius: 3px;
}
</style>
