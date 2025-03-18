<script>
let count = $state(0);

function increment (){

    count+=1;
}
</script>

<h1 >
hii {count}
</h1>

<button onclick={increment}>
Click me
</button>