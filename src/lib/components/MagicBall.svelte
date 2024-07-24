<div>
    <button on:click={spin}>Spin</button>

    <div>
        {#key text}
        <p transition:fly={{ x: 200, duration: 500 }}>
            {text}
        </p>
        {/key}
    </div>
</div>

<script>
import { fly } from 'svelte/transition'

let text = 'Spin Me!'

const answers = [
    'Whoa',
    'Yes',
    'No',
    'Maybe',   
    'Never',
    'Don\'t be ridiculous',   
]

const spin = () => {
    text = answers[random_int(answers.length)]
};

/**
 * 
 * @param {number} max
 */
const random_int = (max) => Math.floor(Math.random() * max)
</script>

<style>
div {
    display: flex;
    flex-direction: column;
    align-content: center;
}

p {
    position: absolute;
    text-align: center;
    font-size: 4rem;
}
</style>