<div>
    <form>
        <label for="fname">First name</label>
        <input type="text" id="fname" placeholder="First name" bind:value={fname} required>
        <label for="lname">Last name</label>
        <input type="text" id="lname" placeholder="Last name" bind:value={lname} required>
        <label for="age">Age</label>
        <input type="number" id="age" placeholder="Age" bind:value={age} min="0" required>
        
        <input type="submit" name="" id="" on:click={submit}>
    </form>
</div>

<script>
import { createEventDispatcher } from "svelte";

let fname = '';
let lname = '';
// Can i create a setter?
let age = '';

const dispatch = createEventDispatcher();

const submit = () => {
    // is double number safety necessary
    if (fname && lname && !isNaN(Number(age))) {
        dispatch('add', {
            firstName: fname,
            lastName: lname,
            age: Number(age),
        });
    }
};
</script>