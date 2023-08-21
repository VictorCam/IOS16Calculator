<script>
    import {onMount} from 'svelte'

    const buttons = [
        '(',
        ')',
        'mc',
        'm+',
        'm-',
        'mr',
        'AC',
        '+/-',
        '%',
        '÷',
        '2nd',
        'X^2',
        'X^3',
        'X^Y',
        'e^x',
        '10^x',
        '7',
        '8',
        '9',
        'x',
        '1/x',
        '2/x',
        '2/x',
        'y/x',
        'ln',
        'log10',
        '4',
        '5',
        '6',
        '-',
        'x!',
        'sin',
        'cos',
        'tan',
        'e',
        'EE',
        '1',
        '2',
        '3',
        '+',
        'Rad',
        'sinh',
        'cosh',
        'tanh',
        'pi',
        'Rand',
        '0',
        '.',
        '=',
    ]

</script>

<div class="container">
    <div class="display">
        <p>1111111123.456</p>
    </div>
    <div class="buttons">
        {#each buttons as button, i}
            {#if 9 <= i % 10 || i == buttons.length-1}
                <button class="orange">{button}</button>
            {:else if 6 <= i % 10 && i > 10}
                <button class="gray">{button}</button>
            {:else if 6 <= i % 10}
                <button class="blue">{button}</button>
            {:else}
                <button class="additional">{button}</button>
            {/if}
        {/each}
    </div>
</div>

<style>

    :root {
        --black: #000;
        --matte: #222;
        --gray: #333;
        --steel: #555;
        --white: #fff;
        --orange: #ff6600;
        font-family: Arial, Helvetica, sans-serif;
    }

    .container {
        display: grid;
        grid-template-rows: repeat(2, auto);
    }

    .blue {
        background: var(--steel);
    }

    .gray {
        background: var(--gray);
    }

    .orange {
        background: var(--orange);
    }

    /* take two for this 0th button */
    button:nth-child(47) {
        justify-content: left;
        padding-left: 45px;
        width: 100%;
        border-radius: 40px;
        color: var(--white);
        grid-column: span 2;
    }

    .display {
        direction: rtl;
        color: var(--white);
        font-size: 100px;
    }

    .buttons {
        display: grid;
        grid-template-columns: repeat(10, auto);
        align-items: center;
        grid-gap: 10px;
        justify-content: center;
    }

    button {
        background-color: var(--matte);
        color: var(--white);
        display: inline-block;
        cursor: pointer;
        border-radius: 50%;
        width: 5ch;
        height: 5ch;
        scale: 100%;
        border: 0;
        font-size: 50rem;
        /* font-weight: bold; */
    }

    /* check when the height is more than the width */

    @media (orientation: portrait) {
        .buttons {
            grid-template-columns: repeat(4, 1fr);
            justify-items: center;
        }


        .additional {
            display: none;
        }
    }
</style>