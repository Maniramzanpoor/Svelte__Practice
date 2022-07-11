<script>
  let name;
  let lastName;
  let age;
  let beltColor;
  const submitHandler = () => {
    let newPeople;
    // console.log(name, lastName, age, beltColor);
    newPeople = {name, lastName, age, beltColor};
  };
</script>

<main>
  <div>
    <form on:submit|preventDefault={submitHandler}>
      <input type="text" placeholder="NAME" bind:value={name} />
      <input type="text" placeholder="LastName" bind:value={lastName} />
      <input type="number" placeholder="age" bind:value={age} />
      <select bind:value={beltColor}>
        <option value="red">red</option>
        <option value="black">black</option>
        <option value="blue">blue</option>
        <option value="green">green</option>
      </select>
      <button type="submit">Login Person</button>
    </form>
  </div>
</main>

<style>
  div {
    width: max-content;
    height: max-content;
    border: 1px purple solid;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    align-content: center;
    animation-name: example;
    animation-duration: 4s;
  }
  @keyframes example {
    div {
      margin-top: 700px;
    }
  }
  form {
    padding: 15px;
    border-radius: 20px;
    width: 250px;
  }
  form input {
    width: 250px;
    /* border: orangered 2px solid; */
    /* color: orangered; */
    border-radius: 10px;
    font-weight: bold;
  }
  form input::placeholder {
    font-weight: bold;
    /* color: orangered; */
  }
  form button {
    width: 250px;
    border: none;
    background-color: orangered;
    color: #000;
    font-weight: bold;
    border-radius: 30px;
    cursor: pointer;
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2),
      0 6px 20px 0 rgba(0, 0, 0, 0.19);
  }
  form button:hover {
    box-shadow: 0 12px 16px 0 rgba(0, 0, 0, 0.24),
      0 17px 50px 0 rgba(0, 0, 0, 0.19);
  }
</style>
