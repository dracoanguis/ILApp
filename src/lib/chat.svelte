<script lang="ts">
    import { Card, GradientButton, Input, Toast } from "flowbite-svelte";

    let message_list: [number,string][] = [
        [0, "Hello, I’m IvaBot! 👋 I’m your personal shopping assistant. How can I help you?"],
        [1, "Find me a colorful dress"],
        [0, "Here are some colorful dresses available on our platform"]
    ];

    let notif = false;

</script>


<Card class="shadow-md m-4 max-w-full flex-col justify-between relative">
    <div class="flex flex-col flex-wrap">
        {#each message_list as message}
            {#if message[0] == 0}
                <Card class="my-2">
                    {message[1]}     
                </Card>
            {:else}
                <Card class="place-self-end my-2" color="purple">
                    {message[1]}
                </Card>
            {/if}
        {/each}
    </div>
    <div class="flex flex-row my-2 gap-5">
        <Input placeholder="Your message" color=""/>
        <GradientButton shadow color="purple" pill on:click={() => notif=true}>
            Send
        </GradientButton>
    </div>
    <Toast color="red" position="bottom-left" open={notif} on:close={() => notif=false}>
        <svelte:fragment slot="icon">
            <img src="/ivabot.svg" alt="sad face"/>
        </svelte:fragment>
        Not yet implemented
    </Toast>
</Card>