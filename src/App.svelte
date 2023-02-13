<script>
  import Element from "./lib/Element.svelte";
  import { stringsToElements } from "./periodicTable";
  import debounce from "lodash/debounce";

  let inputValue = "";
  let answers;

  const runTheFunction = debounce((inputValue) => {
    if (inputValue) answers = stringsToElements(inputValue.toLowerCase());
  }, 750);

  $: {
    runTheFunction(inputValue);
    if (!inputValue) {
      answers = null;
    }
  }
</script>

<main>
  <input bind:value={inputValue} />
  {#if !inputValue}
    <p>Type something!</p>
  {:else if !answers}
    <p>loading</p>
  {:else if !answers.length}
    <p>Sorry there is no possible combination.</p>
  {:else}
    <div class="answers">
      {#each answers as answer}
        <div class="answer">
          {#each answer as elementName}
            <Element {elementName} />
          {/each}
        </div>
      {/each}
    </div>
  {/if}
</main>

<style>
  .answers {
    display: flex;
    flex-direction: column;
  }

  .answer {
    margin: 16px;
    display: flex;
    gap: 8px;
    overflow-x: auto;
    max-width: 100%;
  }
</style>
