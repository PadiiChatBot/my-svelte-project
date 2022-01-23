<style></style>

<script>
let name;
</script>

<!--some from Angular-->

<section>
  <h2>Bindings</h2>

  <input bind:value="{name}" placeholder="name" />

  {#if !!name}
    <p>Hello {name}</p>
  {/if}
</section>
