<script>
  //List of Events Modifier :

  //Once : this will only fire once
  //preventDefault : prevent default action or behavior
  // self : only fires event if the clicked element is the target

  export let showModal = false;
  export let isPromo = false;
</script>

{#if showModal}
  <!-- Plain on click will forward the event into function defined in root
    component -->
  <div class="backdrop" on:click|self>
    <div class="modal" class:promo={isPromo}>
      <slot name="title" />
      <slot name="content" />
    </div>
  </div>
{/if}

<style>
  .backdrop {
    width: 100%;
    height: 100%;
    position: fixed;
    background: rgba(0, 0, 0, 0.8);
  }

  .modal {
    padding: 10px;
    border-radius: 10px;
    max-width: 400px;
    margin: 10% auto;
    background: white;
  }

  .promo {
    background: crimson;
    color: white;
  }
</style>
