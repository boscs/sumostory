<script>
    export let titleHat;
    export let mainTitle;
    export let subTitle;
    export let fontSize;
    export let focedHeight;
    fontSize = fontSize || 2;

    const totalHWratio = 1318 / 834;
    const partialHWratio = 970 / 834;
    const mainFontRatio = 239 / 834;
    const hatFontFontRatio = 142 / 834;

    const imgHeight = ((fs, mfr) => {
        const myRegexp = /^(\d*.?\d*)(rem|px|em)?$/g;
        const match = myRegexp.exec(String(fs));
        if (match != null) return (parseFloat(match[1]) / mfr) + (match[2] || "rem");
        else Error("You must pass a fontSize in rem or px");
    })(fontSize, mainFontRatio)
    console.log(fontSize)
    console.log(imgHeight)
</script>
<style>
    /* style ={"height:"+ imgheight+"rem;"}  */
    div {
        display: block;
        color: white;
        filter: invert(42%) sepia(93%) saturate(1352%) hue-rotate(15deg) brightness(119%) contrast(119%);
        
        

    }

    div * {
        position: absolute;
    }

    div img {
        top: 0;
        left: 0;
        height: 1em;
    }

    .mainTitle * {
         white-space: nowrap;
        text-transform: capitalize;
        font-size: calc(239em/834);
        font-variant: small-caps;
    }

    .titleHat * {
        text-transform: uppercase;
        font-size: calc(142em/834);
    }

    .subTitle * {
        text-transform: uppercase;
        font-size: calc(70em/834);
    }

    .mainTitle {
        top: calc(295em/834);
        left: calc(990em/834);

        /* transform: translate(,); */
    }

    .titleHat {
        top: calc(42em/834);
        left: calc(1386em/834);
    }

    .subTitle {
        top: calc(640em/834);
        left: calc(1340em/834);
    }

    h1,
    h2,
    h3,
    p {
        margin: 0;
        padding: 0;
    }
</style>
<div style={"font-size:" + imgHeight + ";height:" + imgHeight + ";" }>
    <img src="./LOGO.png" alt="Logo fab-lab barséquané" />
    <div class="titleHat">
        <p>{titleHat}</p>
    </div>
    <div class="mainTitle">
        <p>
            <slot>{mainTitle}</slot>
        </p>
    </div>
    <div class="subTitle">
        <p>{subTitle}</p>
    </div>
</div>