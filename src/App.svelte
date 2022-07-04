<script>
  let person = [
    { name: "Mani", age: "16", id: "0", beltColor: "red" },
    { name: "Mahan", age: "12", id: "1", beltColor: "blue" },
    { name: "Hoda", age: "41", id: "2", beltColor: "black" },
  ];

  const clickHandlerFunc = (id) => {
    person = person.filter((person) => person.id != id);
  };
</script>

<main>
  {#each person as person (person.id)}
    <div>
      <h1>{person.name}</h1>
      <p>age is : {person.age} beltColor is : {person.beltColor}</p>
      <!-- inLine event Handler -->
      <button on:click={() => clickHandlerFunc(person.id)}>Delete</button>
    </div>
  {:else}
    <h1>there is no people to show ...</h1>
  {/each}
</main>
