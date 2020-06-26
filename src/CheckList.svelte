<script type="text/javascript">
export let tasks;
</script>

<div class="checklist">
  <ul>
    {#each tasks as task}
    <li class="task">
      <input type="checkbox" checked={task.done} />
      {task.name}
      <a href="#" class="remove" />
    </li>
    {/each}
  </ul>
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
</style>
