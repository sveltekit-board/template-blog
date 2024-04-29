<script lang="ts">
    export let head: string = "";
    export let align: "left" | "center" | "right" = "center";
</script>

<section>
    {#if head}
        <div class="head">
            {head}
        </div>
    {/if}
    <div
        class="body"
        class:align-left={align === "left"}
        class:align-center={align === "center"}
        class:align-right={align === "right"}
    >
        <slot />
    </div>
</section>

<style>
    section {
        width: 100%;

        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .head {
        width: 100%;
        height: 40px;

        color: black;

        display: flex;
        justify-content: flex-start;
        align-items: center;

        font-weight: bold;

        font-size: 15px;

        border-bottom: 1px solid black;
    }

    .body {
        width: 100%;

        padding-top: 15px;
        padding-bottom: 15px;
        padding-left:10px;
        padding-right: 10px;

        box-sizing: border-box;

        font-size: 14px;

        display:flex;
        flex-direction: column;
    }

    .align-left {
        align-items: flex-start;
    }
    .align-center {
        align-items: center;
    }
    .align-right {
        align-items: flex-end;
    }
</style>
