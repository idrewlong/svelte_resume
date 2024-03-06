<script>
	import { fade } from 'svelte/transition';
        import { onMount } from 'svelte';
	let visible = false;

        onMount(() => {
        // Set visible to true after a short delay to trigger the fade-in transition
        setTimeout(() => {
            visible = true;
        }, 200);
    });
</script>

<header class="shadow-lg bg-gradient-to-br from-red-600 to-zinc-600 min-h-[30rem] rounded-md mb-8 flex justify-center items-center mt-6 relative p-3 overflow-hidden max-w-5xl mx-auto">
        <!-- <img class="absolute left-0 top-0 min-h-full min-w-full" src="" alt=""> -->
        {#if visible}
        <div transition:fade class="relative text-white"  >
                <h2 class="text-5xl md:text-6xl font-light mb-2 text-center uppercase">Welcome to my 
                        <span class="font-bold">portfolio</span>
                </h2>
                <p class="text-gray-100 text-lg text-center">Web developer proficient in Svelte and Tailwind CSS!</p>
        </div>
        {/if}
</header>
