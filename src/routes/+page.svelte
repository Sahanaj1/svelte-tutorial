<!-- <script>
  import Header from "./Header.svelte";
  let count = $state(0);

  function increment() {
    count += 1;
    console.log(name,'name')
  }
  let name= $state();
</script>

<Header {name} />
<h1>hii {count}</h1>
<button onclick={increment}> Click me </button>
<input bind:value={name} type="text"/> -->

<script>
    import Header from "./Header.svelte";

    let formState = $state({
        name: '',
        birthday: '',
        step:0,
        error:'',
    });
</script>


<Header name={formState.name}/>

{#if formState.error!==""}
<p style="color:red;">{formState.error}</p>
{/if}
<h1>Step: {formState.step}</h1>
<main>
    {#if formState.step==0}
    <form>
        <label for="name">Name:</label>
        <input type="text" id="name" bind:value={formState.name}/>
        <br>
        <button onclick={()=>{
            if (formState.name !==''){
                formState.step +=1;
                formState.error = "";
            }else{
                formState.error = "Please enter your name"
            }
        }}>next</button>
    </form>
    {:else if formState.step==1}
    <form>
        <label for="birthday">Birthday:</label>
        <input type="date" id="birthday" bind:value={formState.birthday}/>
        <br>
        <button onclick={()=>{
            if (formState.birthday !==''){
                formState.step +=1;
                formState.error = "";
            }else{
                formState.error = "Please select your bday"
            }
        }}>next</button>
    </form>
    {/if}
</main>
