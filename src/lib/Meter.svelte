<script lang="ts">
  import Counter from "./Counter.svelte";
  import { currentMeter, totalMeter, intScore, wisScore } from "./stores";

  function getModifier(baseMod: number) {
    if (baseMod < 12) return 1;
    if (baseMod < 14) return 2;
    if (baseMod < 16) return 3;
    if (baseMod < 18) return 4;
    if (baseMod < 22) return 5;
    if (baseMod < 24) return 6;
    if (baseMod < 26) return 7;
    if (baseMod < 28) return 8;
    if (baseMod < 30) return 9;
    if (baseMod < 32) return 10;
    return 0;
  }

  $: $totalMeter = getModifier($intScore) + getModifier($wisScore) + 5;
</script>

<div class="meter-progress">
  {$currentMeter > $totalMeter ? "MADNESS" : `${$currentMeter}/${$totalMeter}`}
</div>
<div class="meter-area">
  <Counter text={"-"} increase={false} />
  <div class="meter-outline">
    <div class="meter-body">
      <div
        class="meter-body-fill"
        style="height: {$currentMeter <= $totalMeter
          ? ($currentMeter / $totalMeter) * 100
          : 100}%"
      />
    </div>
    <div class="meter-base">
      <svg
        class="skull-base"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 512 512"
      >
        <path
          fill="#ADD8E6"
          d="M416 398.9c58.5-41.1 96-104.1 96-174.9C512 100.3 397.4 0 256 0S0 100.3 0 224c0 70.7 37.5 133.8 96 174.9c0 .4 0 .7 0 1.1v64c0 26.5 21.5 48 48 48h48V464c0-8.8 7.2-16 16-16s16 7.2 16 16v48h64V464c0-8.8 7.2-16 16-16s16 7.2 16 16v48h48c26.5 0 48-21.5 48-48V400c0-.4 0-.7 0-1.1zM224 256c0 35.3-28.7 64-64 64s-64-28.7-64-64s28.7-64 64-64s64 28.7 64 64zm128 64c-35.3 0-64-28.7-64-64s28.7-64 64-64s64 28.7 64 64s-28.7 64-64 64z"
        />
      </svg>
      <div class="meter-base-fill" />
    </div>
  </div>
  <Counter text={"+"} increase={true} />
</div>

<style>
  .meter-progress {
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 2rem;
    height: 3rem;
  }

  .meter-area {
    display: flex;
    flex-direction: row;
    align-items: end;
    justify-content: center;
    height: 98%;
    width: 100%;
  }

  .meter-outline {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100%;
    width: 8em;
  }

  .meter-body {
    display: flex;
    justify-content: center;
    align-items: end;
    height: 95%;
    width: 5em;
    background: lightblue;
    border-radius: 0.25rem;
  }

  .meter-body-fill {
    width: 4.5em;
    background: blue;
    z-index: 1;
  }

  .skull-base {
    z-index: 2;
  }
  .meter-base {
    margin-top: -4rem;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .meter-base-fill {
    display: relative;
    position: absolute;
    height: 5em;
    width: 5em;
    background: blue;
    border-radius: 50%;
    z-index: 1;
    box-shadow: 0px 0px 50px 0px lightskyblue;
    animation: skullGlow 4s reverse infinite;
    /* increase last number for intensity */
  }

  @keyframes skullGlow {
    0% {
      box-shadow: 0px 0px 50px 0px lightskyblue;
    }
    50% {
      box-shadow: 0px 0px 50px 20px lightskyblue;
    }
    100% {
      box-shadow: 0px 0px 50px 0px lightskyblue;
    }
  }
</style>
