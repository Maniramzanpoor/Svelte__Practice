<script>
  import Modal from './Components/Modal.svelte';
  import Login from './Components/Login.svelte';

  let People = [
    {name: 'Ali', lastName: 'rmp', age: 14, beltColor: 'red', id: '0'},
    {name: 'Raha', lastName: 'alikahni', age: 23, beltColor: 'green', id: '1'},
    {name: 'Amin', lastName: 'shojaei', age: 54, beltColor: 'blue', id: '2'},
    {name: 'Mammad', lastName: 'marzban', age: 32, beltColor: 'black', id: '3'}
  ];
  const deletePersonFunc = id => {
    // console.log(e.target);
    People = People.filter(Person => Person.id != id);
  };
  function showModal() {
    showModal = !showModal;
  }
  // console.log(newPeople);
</script>

<Modal {showModal}>
  <Login />
</Modal>
<main>
  <button on:click={toggleModal}>ShowModal</button>
  <div class="Person__Data__Element">
    {#each People as Person (Person.id)}
      <div class="Person__Data__Active">
        <h1>{Person.name}{Person.lastName}</h1>
        <h2>{Person.age}</h2>
        <p>{Person.beltColor}</p>
        <button on:click={() => deletePersonFunc(Person.id)}>Delete</button>
      </div>
    {:else}
      <h1>there is no people to show ...</h1>
    {/each}
  </div>
</main>

<style>
  main {
    top: 0;
    display: flex;
    /* padding: 3rem; */
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .Person__Data__Element {
    display: flex;
  }
  .Person__Data__Active {
    padding-left: 5rem;
  }
</style>
