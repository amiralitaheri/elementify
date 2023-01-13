<script>
    import { periodicTableMap } from "../periodicTable";
    export let elementName;

    const element = periodicTableMap[elementName];
</script>

<div class="container">
    <div class="symbol">{element.symbol}</div>
    <div class="number info">{element.number}</div>
    <div class="atomic-mass info">{element.atomic_mass}</div>
</div>

<style>
    .container {
        position: relative;
        background: var(--font-color);
        color: var(--background-color);
        width: 6rem;
        height: 6rem;
        display:flex;
        align-items: center;
        justify-content: center;
    }

    .symbol {
        font-size: 2rem;
    }

    .info {
        position: absolute;
        left: 0;
        padding: 2px;
        font-size: 1rem;
    }

    .number {
        top: 0;
    }

    .atomic-mass {
        bottom: 0;
    }
</style>
