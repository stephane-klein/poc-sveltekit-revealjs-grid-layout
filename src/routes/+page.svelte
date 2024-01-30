<script>
    import { onMount, tick } from "svelte";
    import "reveal.js/dist/reveal.css";
    import "reveal.js/dist/theme/black.css";

    import SlideGridLayout from "$lib/SlideGridLayout.svelte";

    onMount(async () => {
        await tick();
        const Reveal = (await import("reveal.js")).default;

        const deck = new Reveal({
            slideNumber: true,
            center: false
        });
        deck.initialize();
    });
</script>

<svelte:head>
    <title>Slide super titre</title>
</svelte:head>

<div class="reveal">
    <div class="slides">
        <section>
            <SlideGridLayout>
                <span slot="main" class="center"><h2>Title 2</h2></span>
                <span slot="bottom-left"><img src="https://sklein.xyz/_app/immutable/assets/avatar.iAdKzKwE.avif" /></span>
            </SlideGridLayout>
        </section>
        <section>
            <SlideGridLayout>
                <span slot="top-left">Top left</span>
                <span slot="top">Top middle</span>
                <span slot="top-right">Top right</span>
                <span slot="main" class="center"><h2>Title 2</h2></span>
                <span slot="bottom-left"><img src="https://sklein.xyz/_app/immutable/assets/avatar.iAdKzKwE.avif" /></span>
                <span slot="bottom">Bottom middle</span>
                <span slot="bottom-right">Bottom right</span>
            </SlideGridLayout>
        </section>
    </div>
</div>

<style>
    :global(.reveal .slides > section) {
        height: 100%;
    }

    .center {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100%;
    }
    :global(.top-left img, .top img, .top-right img, .bottom-left img, .bottom img, .bottom-right img) {
        margin: 0;
     }
</style>
