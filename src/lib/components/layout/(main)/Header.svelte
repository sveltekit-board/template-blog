<script>
    import HeaderItem from "./HeaderItem.svelte";

</script>
<header>
    <div class="left">
        <HeaderItem href="/">Home</HeaderItem>
        <HeaderItem href="/about">About</HeaderItem>
        <HeaderItem href="/article">Article</HeaderItem>
    </div>
    <div class="right">
        <slot name="right"/>
    </div>
</header>


<style>
    header{
        width:100%;

        background-color: black;

        display:flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;

        height:55px;

        position:sticky;
        top:0;
    }

    .left, .right{
        display:flex;
    }

    .left{
        flex-direction: row;
        justify-content: flex-start;
        padding-inline-start: 60px;

        column-gap: 30px;
    }

    .right{
        flex-direction: row-reverse;
        justify-content: flex-start;
        padding-inline-end: 60px;

        column-gap: 30px;
    }
</style>
