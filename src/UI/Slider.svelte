<script>
    export let min = 0;
    export let max = 2000;
    export let value = '';
    export let size = '';
    export let behavior = '';
    export let playSound = false;

    const sounds = [];
    for (let i = 0; i < 2; i++) {
        sounds[i] = new Audio(`/sounds/AIRY${i}.mp3`);
    }

    const playSoundNow = () => {
        if (playSound) {
            const i = Math.floor(Math.random() * 2);
            sounds[i].play();
        }
    };

</script>

<input
    type="range"
    on:mousedown={()=>playSoundNow()}
    non-draggable
    class={`${size} ${behavior}`}
    min={min}
    max={max}
    bind:value={value}/>

<style>
    .expand {
        flex-grow: 1;
    }

    input {
        -webkit-appearance: none;
        appearance: none;
        display: block;
        margin: 0.5rem 0;
        outline: none;
        border-radius: 2px;
        cursor: auto;
        padding: 6px 6px 6px 10px;
        transition: all 0.3s cubic-bezier(.25,.8,.25,1);
        padding: 0;
        margin: 1rem 0;
        height: 0.3rem;
        background: rgb(225, 225, 225);
    }

    input::-webkit-slider-thumb {
        transition: all 0.3s cubic-bezier(.25,.8,.25,1);
        border: 3px solid #4a5b63dd;
        box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
        -webkit-appearance: none;
        appearance: none;
        border-radius: 50%;
        background: rgb(240, 240, 240);
        width: 1.25rem;
        height: 1.25rem;
        padding: 0;
        margin: 0;
    }

    input::-webkit-slider-thumb:active {
        transform: scale(1.05, 1.05);
    }

    input:not(:focus)::-webkit-slider-thumb:hover {
        box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
    }

    input:focus::-webkit-slider-thumb {
        box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
    }

    input::-moz-range-thumb {
        transition: all 0.3s cubic-bezier(.25,.8,.25,1);
        border: 3px solid #4a5b63dd;
        box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
        -webkit-appearance: none;
        appearance: none;
        border-radius: 50%;
        background: rgb(240, 240, 240);
        width:0.95rem;
        height: 0.95rem;
        padding: 0;
        margin: 0;
    }

    input::-moz-range-thumb:active {
        transform: scale(1.05, 1.05);
    }

    input:not(:focus)::-moz-range-thumb:hover {
        box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
    }

    input:focus::-moz-range-thumb {
        box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
    }
</style>