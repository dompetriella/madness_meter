<script>
  export let text;
  export let increase;

  function counterClick() {
    if (increase) return console.log("increase");
    console.log("decrease");
  }
</script>

<button on:click={counterClick} class="counter"> {text} </button>

<style>
  .counter {
    margin: 1em;
    height: 3em;
    width: 3em;
    background: white;
    color: black;
    font-weight: bold;
    font-size: medium;
    border: none;
    border-radius: 0.5rem;
    box-shadow: inset 0px -5px grey;
  }
</style>
