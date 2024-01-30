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
            center: false,
            hash: true
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
        <section>
            <SlideGridLayout>
                <span slot="main" class="page">
                    <h3>Agenda</h3>

                    <ul>
                        <li class="fragment">Subject 1</li>
                        <li class="fragment">Subject 2</li>
                        <li class="fragment">Subject 3</li>
                        <li class="fragment">Subject 4</li>
                        <li class="fragment">Subject 5</li>
                    </ul>
                </span>
            </SlideGridLayout>
        </section>
    </div>
</div>

<style>
    :global(.reveal .slides > section) {
        height: 100%;
    }

    :global(.reveal .slides) {
        text-align: left;
    }

    :global(.reveal H3) {
        border-left: 0.1em solid var(--r-link-color-dark);
        padding-left: 0.2em;
    }

    :global(.reveal UL) {
        margin: 0.3em;
        font-size: 0.8em;
    }

    :global(.reveal UL LI) {
        margin-bottom: 0.5em;
    }

    .page {
        min-height: 80%;
    }

    .center {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100%;
        width: 100%;
    }
    :global(.top-left img, .top img, .top-right img, .bottom-left img, .bottom img, .bottom-right img) {
        margin: 0;
     }
</style>
