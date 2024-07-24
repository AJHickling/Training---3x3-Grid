<p>{hour} : {minutes} : {seconds}</p>

<script>
var date = new Date();
setInterval(() => {
    date = new Date();
}, 1000);

$: hour = date.getHours().toString().padStart(2, '0');
$: minutes = date.getMinutes().toString().padStart(2, '0');
$: seconds = date.getSeconds().toString().padStart(2, '0');

</script>