<div>
    {#if current < quiz.length}
        <p>{quiz[current].question}</p>
        <div>
            {#each quiz[current].options as option, i}
                <button on:click={option.answer ? correct : incorrect}>{option.text}</button>
            {/each}
        </div>
    {:else}
        <div>
            Completed!
        </div>
    {/if}
    <p>Answer: {current}</p>
</div>


<script>
let current = 0;

const quiz = [
    {
        question: 'What is 7 + 9',
        options: [
            {text: '5', answer: false},
            {text: '-2', answer: false},
            {text: '16', answer: true},
            {text: '17', answer: false},
        ]
    },
    {
        question: 'What is 11 * 3',
        options: [
            {text: '33', answer: true},
            {text: '14', answer: false},
            {text: '6', answer: false},
            {text: 'cat', answer: false},
        ]
    },
    {
        question: 'What is 7 - 17',
        options: [
            {text: '-19', answer: false},
            {text: '-10', answer: true},
            {text: '10', answer: false},
            {text: '3', answer: false},
        ]
    },
    {
        question: 'What is 36 / 9',
        options: [
            {text: '6', answer: false},
            {text: '27', answer: false},
            {text: '5', answer: false},
            {text: '4', answer: true},
        ]
    },
];

const correct = () => current++;
const incorrect = () => current = 0;


</script>

<style>

</style>