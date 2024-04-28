<script lang="ts">
    import Header from "$lib/components/layout/index/Header.svelte";
    import HeaderItem from "$lib/components/layout/index/HeaderItem.svelte";
    import Logo from "$lib/components/layout/index/Logo.svelte";

    
</script>

<Logo title={"Blog"}/>
<Header>
    <svelte:fragment slot="left">
        <HeaderItem href="/">Home</HeaderItem>
        <HeaderItem href="/about">About</HeaderItem>
        <HeaderItem href="/article">Article</HeaderItem>
    </svelte:fragment>
</Header>
<div class="container">
    <main>
        <slot/>
    </main>
</div>

<style>
    .container{
        display:flex;
        flex-direction: row;
        justify-content: center;
        align-items: flex-start;
        flex-wrap: wrap;
    }
</style>