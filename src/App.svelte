<script>
  import Modal from "./Modal.svelte";
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
  let showModal = false;
  let num = 70;

  const toggleModal = () => {
    showModal = !showModal;
  };
</script>

<Modal
  {showModal}
  content="This is a prop named content"
  on:click={toggleModal}
>
  <h3>Add A New Person</h3>
  <form>
    <input type="text" placeholder="name" />
    <input type="text" placeholder="belt" />
    <button>Add Person</button>
  </form>
</Modal>
<main>
  <button on:click={toggleModal}>Open Modal</button>
  {#if num > 20}
    <p>Greater than 20</p>
  {:else if num > 5}
    <p>Greater than 5</p>
  {/if}
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
