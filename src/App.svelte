<script>
  import StatsInput from "./lib/StatsInput.svelte";
  import Meter from "./lib/Meter.svelte";
  import SpellButton from "./lib/SpellButton.svelte";
  import { intScore, wisScore } from "./lib/stores";
</script>

<main>
  <div class="stats-input">
    <StatsInput name={"INT"} score={$intScore} />
    <StatsInput name={"WIS"} score={$wisScore} />
  </div>
  <div class="meter">
    <Meter />
  </div>
  <div class="spell-buttons">
    <SpellButton name={"Thought"} />
    <SpellButton name={"Scheme"} />
    <SpellButton name={"Machination"} />
  </div>
</main>

<style>
  .stats-input {
    height: 12vh;
    display: flex;
    justify-content: space-evenly;
    align-items: flex-start;
  }

  .meter {
    height: 74vh;
  }

  .spell-buttons {
    height: 12vh;
    display: flex;
    align-items: end;
    justify-content: space-evenly;
  }
</style>
