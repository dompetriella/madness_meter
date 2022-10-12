<script>
  export let name;
  export let score;
</script>

<div class="statsInputArea">
  <div class="name">{name}</div>
  <input type="text" bind:value={score} />
</div>

<style>
  .statsInputArea {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 10vh;
    width: 40vw;
    padding: 0.5rem;
  }

  .name {
    height: 100%;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: x-large;
  }

  input {
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    font-size: 2rem;
    padding: 0;
    margin: 0;
    height: 100%;
    width: 50%;
    box-shadow: 0px 0px 50px 0px #779cc8;
    border: none;
  }
</style>
