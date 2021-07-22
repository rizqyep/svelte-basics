<script>
  let people = [
    { name: "Abek", beltColour: "Black", age: 21, id: 1 },
    { name: "Ipul", beltColour: "Orange", age: 21, id: 2 },
    { name: "Sesar", beltColour: "Brown", age: 21, id: 3 },
  ];

  const deletePerson = (id) => {
    people = people.filter((person) => {
      return person.id != id;
    });
  };
</script>

<main>
  {#each people as person (person.id)}
    <div class="card">
      <h4>{person.name}</h4>
      <p>{person.beltColour}</p>
      <p>{person.age}</p>

      <button
        on:click={() => {
          deletePerson(person.id);
        }}>Delete</button
      >
    </div>
  {/each}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
    background-color: #dfdfdf;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  .card {
    background-color: #ffffff;
    box-shadow: 1px 1px 10px #cecece 1px 1px 20px #cecece;
    width: 80vw;
    padding: 10px;
    margin: 30px auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
