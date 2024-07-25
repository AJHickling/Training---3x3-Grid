<p>{hour} : {minutes} : {seconds}</p>

<script>
import { onDestroy } from "svelte";

var date = new Date();
const interval = setInterval(() => {
    date = new Date();
}, 1000);

$: hour = date.getHours().toString().padStart(2, '0');
$: minutes = date.getMinutes().toString().padStart(2, '0');
$: seconds = date.getSeconds().toString().padStart(2, '0');

onDestroy(() => clearInterval(interval))

</script>