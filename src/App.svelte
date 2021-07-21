<script>
  let name = "Rep";
  let beltColour = "Black";

  const handleClick = () => {
    if (beltColour == "Black") {
      beltColour = "Orange";
    } else {
      beltColour = "Black";
    }
  };

  const handleInput = (event) => {
    beltColour = event.target.value;
  };
</script>

<main>
  <h1>Hello {name}!</h1>
  <p>
    Belt Colour : {beltColour}
  </p>
  <button on:click={handleClick}>Update Belt Colour</button>
  <!-- <input type="text" on:input={handleInput} value={beltColour} /> -->

  <!-- Two Way Binding ShortCut -->

  <input type="text" bind:value={beltColour} />
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
