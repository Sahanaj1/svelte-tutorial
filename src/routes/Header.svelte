<script lang="ts">
    let {name,fake_name}:{
        name:string,
        fake_name?:string | null
    } = $props();
</script>

<h2>Hello {name}</h2>