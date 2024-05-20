<script lang="ts">
    import Chat from "$lib/chat.svelte";
    import { Canvas } from "@threlte/core";
    import Model from "$lib/model.svelte";
    import { ButtonGroup, GradientButton } from 'flowbite-svelte';

    let model = 0;

</script>

<div class="flex justify-stretch h-full bg-slate-100 relative">
    <div class="half relative">
        <ButtonGroup class="absolute top-5 left-5">
            <GradientButton shadow color="purple" on:click={() => model = 0}>Femme</GradientButton>
            <GradientButton shadow color="purple" on:click={() => model = 1}>Homme</GradientButton>
        </ButtonGroup>
        <Canvas>
            <Model {model}/>
        </Canvas>
    </div>
    <div class="half flex justify-center">
        <Chat />
    </div>
</div>

<style>
    .half {
        width: 50vw;
        height: 91vh;
        /* max-height: 91vh; */
    }
</style>
