<script lang="ts">
    export let head: string = "";
</script>

<section>
    {#if head}
        <div class="head">
            {head}
        </div>
    {/if}
    <div class="body">
        <slot />
    </div>
</section>

<style>
    section {
        width: 100%;

        display: flex;
        flex-direction: column;
        align-items: center;

        background-color: white;
    }

    .head{
        width: 100%;
        height: 40px;

        background-color: black;
        color:white;

        display:flex;
        justify-content: center;
        align-items: center;

        font-weight: bold;

        font-size: 15px;
    }

    .body{
        padding-top:15px;
        padding-bottom: 15px;
    }
</style>
