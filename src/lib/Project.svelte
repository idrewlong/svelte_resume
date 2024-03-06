

<script>
        import { fade } from "svelte/transition";
    
        export let logo = "";
        export let name = "";
        export let description = "name";
        export let stack = "";
        export let width = "";
        export let link = "";
    
        let urlPopup = false;
    
        function toggleUrlPopup(){
            urlPopup = !urlPopup;
        }
</script>

<div class="line"></div>

<!-- //  insert projects here  -->
<div class="relative flex flex-col gap-4 py-6 px-0">
    <img src={logo} alt="" width={width}/>
    <div class="mt-6">
        {#if urlPopup}
            <div class="url" transition:fade>
                {link}
            </div>
        {/if}
        <a class="text-xl font-bold" href={link} target="_blank" on:mouseenter={() => toggleUrlPopup()} on:mouseleave={ () => toggleUrlPopup() }>{name}</a>
    </div>
    <p class="text-md">
        {description}
    </p>

    <div class="flex items-center gap-6 mt-8">
        <img src="/src/assets/svelte.svg" alt="" width="24px"/>
        <p class="text-md">{stack}</p>
    </div>
</div>

<div class="line"></div>

<style>
    
        .url {
            position: absolute;
            border-radius: 8px;
            top: 70px;
            background: rgba(0, 0, 0, 0.5);
            padding: 6px 8px;
            left: -30px;
        }
        
    
        .line {
            background: #2f2f2f;
            height: 1px;
        }
</style>