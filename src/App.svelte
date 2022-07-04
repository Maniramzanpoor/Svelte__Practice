<script>
  let name = "Mani";
  let beltColor = "Black";
  const clickHandler = () => {
    beltColor = "red";
  };
  const inputHandler = (t) => {
    beltColor = t.target.value;
  };
</script>

<main>
  <h1>My Name is : {name}</h1>
  <h2 style="color: {beltColor}">{beltColor}</h2>
  <button on:click={clickHandler}>Update Clicked ME</button>
  <input type="text" on:input={inputHandler} value={beltColor} />
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
