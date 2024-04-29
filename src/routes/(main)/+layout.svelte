<script lang="ts">
    import Aside from "$lib/components/layout/(main)/Aside.svelte";
    import Header from "$lib/components/layout/(main)/Header.svelte";
    import Logo from "$lib/components/layout/(main)/Logo.svelte";
    import { browser } from "$app/environment";
    import { setContext } from "svelte";

    import { writable } from "svelte/store";
    let isMobile = writable<boolean>(false);
    setContext('isMobile', isMobile);
    if(browser){
        $isMobile = window.innerWidth <= 1079
    }

    let isAsideOpened = writable<boolean>(false);
    setContext('isAsideOpened', isAsideOpened);
</script>

<svelte:window on:resize={() => {$isMobile = window.innerWidth <= 1079}}/>

<Logo title={"Blog"} />
<Header />
<div class="container">
    <main>
        <slot />
    </main>
    {#if $isMobile && $isAsideOpened}
        <div class="panel"/>
    {/if}
    <Aside />
</div>

<style>
    @media only screen and (min-width: 1080px) {
        main {
            width: 800px;
        }

        .container {
            display: flex;
            flex-direction: row;
            justify-content: center;
            align-items: flex-start;
            flex-wrap: wrap;

            column-gap: 30px;

            padding-top: 30px;
        }
    }

    @media only screen and (max-width: 1079px){
        main {
            width: 100%;
        }

        .panel{
            position: fixed;
            top:0;
            left:0;

            width:100%;
            height:100%;

            background-color:white;
            opacity: 0.5;

            filter: blur(1px);
        }
    }
</style>
