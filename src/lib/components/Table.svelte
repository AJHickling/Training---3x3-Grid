<div>
    <table>
        <tr>
            <th>First name</th>
            <th>Last name</th>
            <th>Age</th>
            <th></th>
        </tr>
        {#each data as person}
            <tr>
                <td>{person.first_name}</td>
                <td>{person.last_name}</td>
                <td>{person.age}</td>
                <td><button on:click={() => remove(person)}>Remove</button></td>
            </tr>
        {/each}
    </table>
</div>

<script>
// Export (exposing to parent)
/**
 * @type {Person[]}
 */
export let data = [
    {
        first_name: 'John',
        last_name: 'Doe',
        age: 20,
    },
    {
        first_name: 'John',
        last_name: 'Smith',
        age: 0,
    },
    {
        first_name: 'John',
        last_name: 'Jones',
        age: 10,
    },
    {
        first_name: 'Jack',
        last_name: 'Jones',
        age: 2,
    },
    {
        first_name: 'Joel',
        last_name: 'Jones',
        age: 99,
    },
    {
        first_name: 'Jon',
        last_name: 'Jones',
        age: 20,
    },
];

/**
 * 
 * @param {Person} person
 */
const remove = (person) => {
    const index = data.indexOf(person);
    if (index !== -1) {
        data.splice(index, 1);
    }
    data = data;
}
</script>