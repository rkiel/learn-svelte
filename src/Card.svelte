<script type="text/javascript">
export let id;
export let title;
export let description;
export let tasks;

import CheckList from './CheckList.svelte'
</script>

<div class="card">
  <div class="title">{title}</div>
  <div class="details">
    {description}
    <CheckList cardId={id} tasks={tasks} />
  </div>
</div>

<style>
  .card {
    position: relative;
    z-index: 1;
    background: #fff;
    width: 100%;
    padding: 10px 10px 10px 15px;
    margin: 0 0 10px 0;
    overflow: auto;
    border: 1px solid #e5e5df;
    border-radius: 3px;
    box-shadow: 0 1px 0 rgba(0, 0, 0, 0.25);
  }
  .title {
    font-weight: bold;
    border-bottom: solid 5px transparent;
  }
  .title:before {
    display: inline-block;
    width: 1em;
    content: ">";
  }
  .is-open:before {
    content: "v";
  }

</style>
