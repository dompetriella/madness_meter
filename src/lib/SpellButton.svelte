<script>
  export let name;
</script>

<button>
  <div class="name">{name}</div>
</button>

<style>
  button {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: #779cc8;
    height: 5vh;
    width: 30vw;
    padding: 1.5rem 3.2rem;
    border-radius: 0.5rem;
    border: none;
    box-shadow: inset 0px -5px grey;
  }

  .name {
    height: 100%;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 1rem;
    background-color: #130938;
    padding: 1rem 3rem;
    border-radius: 0.5rem;
  }
</style>
