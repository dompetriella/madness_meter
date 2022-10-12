<script lang="ts">
  import { currentMeter } from "./stores";
  export let text: string;
  export let increase: boolean;

  function counterClick() {
    if (increase) return $currentMeter++;
    if ($currentMeter > 0) $currentMeter--;
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
