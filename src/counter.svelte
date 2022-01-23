<style>
</style>

<script>
export let counter;

const onButtonClick = () => {
  counter += 1;
};

$: doubled = counter * 2;

$: quedrupled = doubled * 2;

//not working without reactivity
if (counter >= 13) {
  alert("counter is too high ");

  counter = 5;
}

$: if (counter >= 15) {
  alert("counter is too high ");

  counter = 7;
}
</script>

<section>
  <h2>{counter}</h2>
  <button on:click="{onButtonClick}">click me</button>

  <p>
    {counter} * 2 = {doubled}
  </p>

  <p>
    {doubled} * 2 = {quedrupled}
  </p>

  {#if counter > 9}
    <p>not bad</p>
  {:else}
    <p>it's bad</p>
  {/if}
</section>
