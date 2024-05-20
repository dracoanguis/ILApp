<script lang="ts">
    import Chat from "$lib/chat.svelte";
    import { Canvas } from "@threlte/core";
    import Model from "$lib/model.svelte";
    import { ButtonGroup, Card, GradientButton } from 'flowbite-svelte';

    let model = 0;

</script>

<div class="flex justify-stretch h-full bg-purple-200 relative">
    <div class="half relative">
        <Card class="m-4 max-w-full w-fit h-fit p-0">
            <ButtonGroup class="absolute top-12 left-12">
                <GradientButton shadow color="purple" on:click={() => model = 0}>Femme</GradientButton>
                <GradientButton shadow color="purple" on:click={() => model = 1}>Homme</GradientButton>
            </ButtonGroup>
            <div class="Container">
                <Canvas>
                    <Model {model}/>
                </Canvas>
            </div>
        </Card>
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
    .Container {
        width: 45vw;
        height: 77vh;
    }
</style>
