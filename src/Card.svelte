<script type="text/javascript">
export let id;
export let title;
export let description;
export let tasks;

let showDetails = false;

import CheckList from './CheckList.svelte'
import marked from 'marked'

function onClick() {
  showDetails = !showDetails;
}
</script>

<div class="card">
  <div class={showDetails ? "title is-open" : "title"} on:click={onClick}>{title}</div>
  {#if showDetails}
  <div class="details">
    {@html marked(description)}
    <CheckList cardId={id} tasks={tasks} />
  </div>
  {/if}
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
