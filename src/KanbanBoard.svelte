<script>
import {data} from './data'
import List from './List.svelte'
</script>

<div class="app">
  <List id="todo" title="To Do" cards={data.filter(x => x.status === 'todo')} />
  <List id="in-progress" title="In Progress" cards={data.filter(x => x.status === 'in-progress')} />
  <List id="done" title="Done" cards={data.filter(x => x.status === 'done')} />
</div>

<style>
  :global(*) {
    box-sizing: border-box;
  }
  :global(html,body,#app) {
    height: 100%;
    margin: 0%;
    padding: 0%;
  }
  :global(body) {
    background: #eee;
    font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  }
  :global(h1) {
    font-weight: 200;
    color: #3b414c;
    font-size: 20px;
  }
  :global(ul) {
    list-style-type: none;
    padding: 0;
    margin: 0;
  }
  .app {
    white-space: nowrap;
    height: 100%
  }
</style>
