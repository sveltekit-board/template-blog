<script lang="ts">
    import AsideItem from "./AsideItem.svelte";
    import { getContext } from "svelte";
    import { type Writable } from "svelte/store";

    const isAsideOpened: Writable<boolean> = getContext("isAsideOpened");
    const isMobile: Writable<boolean> = getContext("isMobile");
</script>

<aside class:opened={$isAsideOpened}>
    {#if $isMobile}
        <button on:click={() => {$isAsideOpened = !$isAsideOpened}} class="closer">
            X
        </button>
    {/if}
    <AsideItem head="Profile">
        <img
            src="/assets/img/icons/user.svg"
            alt=""
            width="120px"
            height="120px"
            style="border-radius:50vh;background-color:white;margin-bottom:20px;"
        />
        My Name
    </AsideItem>
    <AsideItem head="Category" align="left">
        <a href="/board/category1"> Category 1 </a>
        <a href="/board/category2"> Category 2 </a>
    </AsideItem>
    <AsideItem head="Contact Me" align="left">
        <div class="row">
            <a href="mailto:">
                <img src="/assets/img/icons/email.svg" class="icon" alt="" />
            </a>
            <a href="https://instagram.com">
                <img
                    src="/assets/img/icons/instagram.svg"
                    class="icon"
                    alt=""
                />
            </a>
            <a href="https://twitter.com">
                <img src="/assets/img/icons/x.svg" class="icon" alt="" />
            </a>
        </div>
    </AsideItem>
</aside>

<style>
    aside {
        width: 250px;

        display: flex;
        flex-direction: column;
        align-items: center;

        row-gap: 30px;

        background-color: #f3f3f3;
    }

    @media only screen and (max-width: 1079px) {
        aside {
            width: 270px;
            max-width: 100%;

            position: fixed;
            top: 0;
            right: 0;

            height: 100%;
            overflow-y: auto;

            padding-left:10px;
            padding-right:10px;
            padding-top: 10px;
            box-sizing: border-box;

            transform: translateX(100%);

            transition: transform 0.2s;
        }

        aside.opened{
            transform: translateX(0);
        }
    }

    a {
        color: black;
        text-decoration: none;
    }
    a:hover {
        color: rgb(122, 122, 122);
    }

    .icon {
        width: 25px;
        height: 25px;
    }

    .row {
        display: flex;
        flex-direction: row;

        column-gap: 10px;
    }

    .closer{
        width: 30px;
        height: 30px;

        border-radius: 0px;
        border: 0;

        background-color: black;

        color:white;

        position:fixed;
        top:0;
        right:0;

        font-size:20px;

        cursor: pointer;
    }
</style>
