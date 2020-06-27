<script>
export let id;
export let title;
export let cards;

import Card from './Card.svelte'
</script>

<div class="list">
  <h1>{title}</h1>
  {#each cards as card (card.id)}
    <Card id={card.id} title={card.title} color={card.color} description={card.description} tasks={card.tasks} />
  {/each}
</div>

<style>
  .list {
    position: relative;
    display: inline-block;
    vertical-align: top;
    white-space: normal;
    height: 100%;
    width: 33%;
    padding: 0 20px;
    overflow: auto;
  }
  .list:not(:last-child):after {
    content: "";
    position: absolute;
    top: 0;
    right: 0;
    width: 1px;
    height: 99%;
    background: linear-gradient(to bottom, #eee 0%, #ccc 50%, #eee 100%) fixed;
  }
</style>
