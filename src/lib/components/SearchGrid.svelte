<div>
    <div class="row">
        <input type="text" bind:value={search} on:input>
        <label>
            Grid View
            <input type="checkbox" bind:checked={grid_view}>
        </label>
    </div>

    <ul class={grid_view ? 'grid' : ''}>
        {#each selection as song}
            <li>
                <img src={song.cover} alt="cover">
                {#if !grid_view}
                    {song.title}
                {/if}
            </li>
        {/each}
    </ul>
</div>

<script>
import Img1 from '$lib/assets/album_covers/optimist.png'
import Img2 from '$lib/assets/album_covers/blood_harmony_deluxe.jpg'
import Img3 from '$lib/assets/album_covers/blood_harmony.png'

const songs = [
    {
        title: 'A Concert Six Months From Now',
        cover: Img1
    },
    {
        title: 'Love is Pain',
        cover: Img1
    },
    {
        title: 'What They\'ll Say about Us',
        cover: Img1
    },
    {
        title: 'Peaches Etude',
        cover: Img1
    },
    {
        title: 'The Kids Are All Dying',
        cover: Img1
    },
    {
        title: 'I Lost a Friend',
        cover: Img2
    },
    {
        title: 'Break My Heart Again',
        cover: Img2
    },
    {
        title: 'Die Alone',
        cover: Img3
    },
    {
        title: 'Let\'s Fall in Love for the Night',
        cover: Img3
    },
];

let search = '';
let grid_view = false;

$: selection = songs.filter(
    song => !search || song.title.toLowerCase().includes(search.toLowerCase().trim())
);

</script>

<style>
li {
    display: flex;
    flex-direction: row;
}

ul {
    position: relative;
    height: 12rem;
    overflow-y: scroll;
}

.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 1fr);
    gap: 1rem;
}

img {
    height: 3rem;
}
</style>