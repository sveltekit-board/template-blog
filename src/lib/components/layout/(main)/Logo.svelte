<script lang="ts">
    export let title: string;
    export let subtitle: string = "";
</script>

<div class="logo">
    <div class="title">
        {title}
    </div>
    {#if subtitle}
        <div class="subtitle">
            {subtitle}
        </div>
    {/if}
</div>

<style>
    .logo {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        height: 200px;
    }

    .title{
        font-size: 70px;
    }
</style>
