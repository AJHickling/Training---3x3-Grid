<main>
    <Clock />
    <Login />
    <Quiz />
    <Table bind:data={table_data}/>
    <AddForm on:add={(event) => add_table_item(event.detail)}/>
    <Prices />
    <Search />
    <SearchGrid />
    <MagicBall />
        
</main>

<script>
import Clock from '$lib/components/Clock.svelte'
import Login from '$lib/components/Login.svelte'
import Quiz from '$lib/components/Quiz.svelte'
import Table from '$lib/components/Table.svelte'
import AddForm from '$lib/components/AddForm.svelte'
import Prices from '$lib/components/Prices.svelte'
import Search from '$lib/components/Search.svelte'
import SearchGrid from '$lib/components/SearchGrid.svelte'
import MagicBall from '$lib/components/MagicBall.svelte'

/**
 * @type {Person[]}
 */
let table_data;

/**
 * 
 * @param {Person} person
 */
const add_table_item = (person) => {
    console.log(person);
    table_data.push(person);
    table_data = table_data; // Refreshes t
};

</script>

<style>
:global(*) {
    padding: 0;
    margin: 0;
}

main {
    /* Layout */
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 1fr);
    gap: 1rem;
    height: 48rem;
    margin: 2rem;
    padding: 2rem;
    box-sizing: border-box;
}
</style>