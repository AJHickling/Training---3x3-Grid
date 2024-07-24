<form on:submit|preventDefault={submitForm}>
    <label for="username">Username</label>
    <input type="text" id="username" bind:value={username} />
    
    <label for="password">Password</label>
    <input type="password" id="password" bind:value={password} />

    <input type="submit" disabled={!username || !password} />

    {#if isLoggedIn}
        <div>Log in SUCCESSFUL</div>
    {/if}
    
</form>

<script>``
let isLoggedIn = false;
const usernameStored = 'andrew';
const passwordStored = 'password';
let username = '';
let password = '';

let submitForm = () => {
    if (username === usernameStored && password === passwordStored) {
        isLoggedIn = true;
    }
}
</script>

