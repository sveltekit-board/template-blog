<script lang="ts">
    export let href:string = '';
    export let imgSrc:string = '';
</script>

<a {href}>
    {#if imgSrc}
        <img src={imgSrc} alt="header logo"/>
    {/if}
    <slot/>
</a>

<style>
    a{
        text-decoration: none;
        color: white;
    }
</style>