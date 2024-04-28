<script lang="ts">
    import Aside from "$lib/components/layout/(main)/Aside.svelte";
    import Header from "$lib/components/layout/(main)/Header.svelte";
    import HeaderItem from "$lib/components/layout/(main)/HeaderItem.svelte";
    import Logo from "$lib/components/layout/(main)/Logo.svelte";

    
</script>

<Logo title={"Blog"}/>
<Header/>
<div class="container">
    <main>
        <slot/>
    </main>
    <Aside/>
</div>

<style>
    main{
        width: 750px;
    }

    .container{
        display:flex;
        flex-direction: row;
        justify-content: center;
        align-items: flex-start;
        flex-wrap: wrap;

        padding-top:30px;
    }
</style>