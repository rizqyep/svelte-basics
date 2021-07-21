<script>
  let firstName = "Rizqy";
  let lastName = "EP";
  let beltColour = "Black";

  //Declaration below are reactive values example
  $: fullName = `${firstName} ${lastName}`;

  //Reactive Statements (Code Blocks will react if values inside it changed or altered)
  $: {
    console.log(beltColour);
    console.log(fullName);
  }

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
  <p>{fullName} {beltColour} Belt</p>
  <input type="text" bind:value={firstName} />
  <input type="text" bind:value={lastName} />
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
