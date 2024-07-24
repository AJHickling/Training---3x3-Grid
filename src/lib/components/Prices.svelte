<table>
    <tr>
        <th>Item</th>
        <th>Price</th>
        <th>Show Price</th>
    </tr>
    {#each items as { name, price , show_price }}
        <tr>
            <td>{name}</td>
            <td>{show_price ? price : ''}</td>
            <td><input type="checkbox" bind:checked={show_price}></td>
        </tr>
    {/each}
    <tr>
        <td>Total:</td>
        <td>{total}</td>
    </tr>
</table>

<script>
let items = [
    {
        name: 'item1',
        price: 123,
        show_price: true
    },
    {
        name: 'item2',
        price: 10,
        show_price: true
    },
    {
        name: 'item3',
        price: 1,
        show_price: true
    },
    {
        name: 'item4',
        price: 5,
        show_price: true
    },
    {
        name: 'item5',
        price: 10,
        show_price: true
    },
];

$: total = items.filter(({ show_price }) => show_price).map(({ price }) => price).reduce((a, b) => a + b, 0);
</script>