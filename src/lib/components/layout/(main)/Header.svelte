<script lang="ts">
    import HeaderItem from "./HeaderItem.svelte";
    import { getContext } from "svelte";
    import { type Writable } from "svelte/store";

    const isMobile: Writable<boolean> = getContext("isMobile");
    const isAsideOpened: Writable<boolean> = getContext("isAsideOpened");
</script>

<header>
    <div class="left">
        <HeaderItem href="/">Home</HeaderItem>
        <HeaderItem href="/about">About</HeaderItem>
        <HeaderItem href="/article">Article</HeaderItem>
    </div>
    <div class="right">
        <slot name="right" />
        <button
            on:click={() => {
                $isAsideOpened = !$isAsideOpened;
            }}
            class="opener"
        >
            <img src="/assets/img/icons/menu.svg" alt="" />
        </button>
    </div>
</header>

<style>
    header {
        width: 100%;

        background-color: black;

        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;

        height: 55px;

        position: sticky;
        top: 0;
    }

    .left,
    .right {
        display: flex;
    }

    .left {
        flex-direction: row;
        justify-content: flex-start;
        padding-inline-start: 60px;

        column-gap: 30px;
    }

    .right {
        flex-direction: row-reverse;
        justify-content: flex-start;
        padding-inline-end: 60px;

        column-gap: 30px;
    }

    .opener {
        display: none;
    }

    @media only screen and (max-width: 1079px) {
        header {
            height: 40px;
        }
        .left {
            padding-inline-start: 20px;
        }
        .right {
            padding-inline-end: 20px;
        }

        .opener {
            width: 30px;
            height: 30px;

            border-radius: 0px;
            border: 0;

            background-color: black;

            color: white;

            font-size: 20px;

            cursor: pointer;

            display: flex;
            justify-content: center;
            align-items: center;
        }
        .opener > img {
            width: 25px;
            height: 25px;
            filter: invert(100%);
        }
    }
</style>
