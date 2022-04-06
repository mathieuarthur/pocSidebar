<script>
    import { fade } from 'svelte/transition';

    let visible = false;

    function toggleVisible()
    {
        visible = !visible
    }
    </script>

<main>
    <div class="container">
        {#if !visible}
        <div class="burger" on:mouseenter={toggleVisible}  transition:fade>
            <div></div>
            <div></div>
            <div></div>
        </div>
        {/if}
    </div>
    <div class={`${visible ? "sidebar" : "sidebar hidden"}`}  on:mouseleave={toggleVisible}> 
        <ul>
            <li>tes</li>
            <li>dsqdqs</li>
            <li>dsqdqs</li>
            <li>fgsdgfd</li>
        </ul>
        <div class="dec">
            <img src="/img/dec.png" alt="saucisse">
        </div>
    </div>
</main>

<style lang="scss">

    @use "./scss/unselectable.scss";
    .container
    {
        position: fixed;
        display: flex;
        align-items: center;
        height: 100%;
        width: 100%;
    }
    .burger
    {    
        margin-left: 5px;
        width: fit-content;
        height: fit-content;
        border: solid 1px black;
        background-color: red;
    }
    .burger div
    {
        display: block;
        background-color: black;
        width:     2em;
        height: 0.3em;
        margin: 5px;
    }
    ul
    {
        list-style: none;
        margin: 0;
        padding: 0;
        cursor: pointer;
    }
    li
    {
        @extend .unselectable;
        color: white;
        padding: 0.5em;
    }

    .sidebar
    {
        display: flex;
        justify-content: center;
        flex-direction: column;
        text-align: center;
        background-color: black;
        height: 100vh;
        width: fit-content;
        position: absolute;
        left: 0px;
        transition: all 1s ease;
    }
    .sidebar.hidden
    {
        left: -200px;
        transition: all 1s ease;
    }
    .dec
    {
        display: flex;
        justify-content: center;
    }
    .dec img
    {
        width: 1.5em;
        height: 1.5em;
        cursor: pointer;
    }
</style> 