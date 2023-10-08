<script>
    import { page } from '$app/stores';
    import { slide } from 'svelte/transition';
    import { quintOut } from 'svelte/easing';
      @type { boolean };
    let open;
    function closeSideBar(e) {
        if (e.key == 'Escape' || e.keycode == 27) {
            open = false
        }
    }
</script>

{ #if open }
    <aside on:keydown={ closeSideBar } on:click|self={() => (open = false)}>
        <nav role="dialog" transition:slide={{ delay:0, duration:1000, easing:quintOut, axis:'x'}}>
            <span id="close" class="fa-solid fa-x" tabindex="0" on:keypress={() => open=false} on:click={() => open=false} role="button"></span>
            <a autofocus href="/" on:keypress={() => (open = false)} on:click={() => (open=false)} aria-current={$page.url.pathname === "/"}>Home</a>
            <a href="/WhatAreCats" on:keypress={() => (open = false)} on:click={() => (open = false)} aria-current={$page.url.pathname === '/WhatAreCats'}>What Are Cats</a>
            <a href="/WhoIsJessie" on:keypress={() => (open = false)} on:click={() => (open = false)} aria-current={$page.url.pathname === '/WhoIsJessie'}>Who Is Jessie</a>
        </nav>
    </aside>
{ /if }

<span class="fa-sold fa-bars navigationToggle" aria-label="navigation toggle" on:keypress={() => (open = !open)} on:click={() => (open = !open)} tabindex="0" role="button"/>

<style>
    .navigationToggle {
        margin: 2vmin;
        font-size: 5vmin;
    }

    #close {
        color: white
    }

    aside {
        display: flex;
        z-index: 1;
        position: fixed;
        top: 0;
        left: 0;
        height: 100dvh;
        width: 100dvw;
        background-color: rgba (0, 0, 0, 0.2);
        backdrop-filter: blur (7px);
    }
</style>