<script lang="ts">
    import Chat from "$lib/chat.svelte";
    import { Canvas, T } from "@threlte/core";
</script>

<div class="flex justify-stretch h-full">
    <div class=" bg-red-500 half">
        jkdjd
    </div>
    <div class="bg-blue-500 half flex justify-center">
        <Chat />
    </div>
</div>

<style>
    .half {
        width: 50vw;
    }
</style>