<script>
  import { periodicTableMap } from "../periodicTable";

  export let elementName;

  const element = periodicTableMap[elementName];
</script>

<div class="container">
  <div class="background" style="background: {'#' + element['cpk-hex']};" />
  <div class="symbol">{element.symbol}</div>
  <div class="number info">{element.number}</div>
  <div class="atomic-mass info">{Math.round(element.atomic_mass)}</div>
</div>

<style>
  .container {
    position: relative;
    color: var(--background-color);
    width: clamp(3rem, 15vw, 6rem);
    height: clamp(3rem, 15vw, 6rem);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    pointer-events: none;
  }

  .background {
    position: absolute;
    z-index: -1;
    width: 100%;
    height: 100%;
    filter: brightness(80%);
  }

  .symbol {
    font-size: clamp(1rem, 5vw, 2rem);
  }

  .info {
    position: absolute;
    left: 0;
    line-height: clamp(0.5rem, 2.5vw, 1rem);
    padding: clamp(2px, 0.5vw, 4px);
    font-size: clamp(0.5rem, 2.5vw, 1rem);
  }

  .number {
    top: 0;
  }

  .atomic-mass {
    bottom: 0;
  }
</style>
