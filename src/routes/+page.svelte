<script>
    import { onMount, tick } from "svelte";
    import "reveal.js/dist/reveal.css";
    import "reveal.js/dist/theme/black.css";

    onMount(async () => {
        await tick();
        const Reveal = (await import("reveal.js")).default;
        console.log(Reveal);

        const deck = new Reveal();
        deck.initialize();
    });
</script>

<svelte:head>
    <title>Slide super titre</title>
</svelte:head>

<div class="reveal">
    <div class="slides">
        <section>
            <h2>Titre 1</h2>
        </section>
        <section>
            <h2>Titre 2</h2>
        </section>
    </div>
</div>
