<div class="slide-grid-layout">
    <div class="top-left">
        <slot name="top-left" />
    </div>
    <div class="top">
        <slot name="top" />
    </div>
    <div class="top-right">
        <slot name="top-right" />
    </div>
    <div class="main">
        <slot name="main" />
    </div>
    <div class="bottom-left">
        <slot name="bottom-left" />
    </div>
    <div class="bottom">
        <slot name="bottom" />
    </div>
    <div class="bottom-right">
        <slot name="bottom-right" />
    </div>
</div>
<style>
    .slide-grid-layout {
        width: 100%;
        height: 100%;
        display: grid;
        grid-template-columns: auto 1fr auto;
        grid-template-rows: auto 1fr auto;
        grid-template-areas: "topleft top topright"
            "main main main"
            "bottomleft bottom bottomright";
    }

    .top-left, .top, .top-right, .bottom-left, .bottom, .bottom-right {
        font-size: 0.5em;
    }
    .top-left {
        grid-area: topleft;
        display: flex;
        align-items: start;
        justify-content: start;
        height: 100%;
    }

    .top {
        grid-area: top;
        display: flex;
        align-items: start;
        justify-content: center;
        height: 100%;
    }

    .top-right {
        grid-area: topright;
        display: flex;
        align-items: start;
        justify-content: end;
        height: 100%;
    }

    .main {
        grid-area: main;
        display: flex;
        align-items: center;
        justify-content: start;
        height: 100%;
    }

    .bottom-left {
        grid-area: bottomleft;
        display: flex;
        align-items: start;
        justify-content: end;
        height: 100%;
    }

    .bottom {
        grid-area: bottom;
        display: flex;
        align-items: end;
        justify-content: center;
        height: 100%;
    }

    .bottom-right {
        grid-area: bottomright;
        display: flex;
        align-items: end;
        justify-content: end;
        height: 100%;
    }
</style>
