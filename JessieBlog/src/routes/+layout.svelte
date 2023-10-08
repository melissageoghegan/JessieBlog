<header>
    <img src="TuxedoCat.png" alt="clipart of a tuxedo cat's face and paws">
    <div>
        <h1>Cat World</h1>
        <p>r a w r</p>
    </div>
</header>
    
<main><slot/></main>

<style>
    @font-face {
        font-family: 'cat 1';
        font-style: normal;
        src: url(Catlove.ttf) format(trueType);
    }
    @font-face {
        font-family: 'cat 2';
        font-style: normal;
        src: url(CatPaw.ttf) format(trueType);
    }
    header {
        display: flex;
        flex-direction: row;
        border: 2vmin ridge #CCD074;
    }
    img {
        height: 50vmin;
    }
    div {
        display: flex;
        flex-direction: column;
        margin: auto;
    }
    h1 {
        text-align: center;
        color: #0C1D13;
        font-size: 70pt;
        font-family: 'cat 1';
        margin: 0;
    }
    :global(h2) {
        text-align: center;
        color: #0C1D13;
        font-size: 40pt;
        margin-bottom: 0;
        text-decoration: 4px underline #CCD074;
    }
    p {
        font-family: 'cat 2';
        margin: 0;
    }
    :global(p) {
        color: #415146;
        text-align: center;
        font-size: 18pt;
    }
</style>