<style></style>

<script>
import "form.css";
let name;
</script>

<!--something from Angular-->

<section>
  <h2>Bindings</h2>

  <input class="example" bind:value="{name}" placeholder="name" />

  {#if !!name}
    <p>Hello {name}</p>
  {/if}
</section>
