<script lang="ts">
    import { ArrowKeyRight, Button, Card, Input } from "flowbite-svelte";

    let message_list: [number,string][] = [
        [0, "Hello, I’m IvaBot! 👋 I’m your personal shopping assistant. How can I help you?"],
        [1, "Find me a colorful dress"],
        [0, "Here are some colorful dresses available on our platform"]
    ];

</script>


<Card class="shadow-md m-10 max-w-full flex-col justify-between">
    <div class="flex flex-col">
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
    <div class="flex flex-row my-2">
        <Input placeholder="Your message"/>
        <Button pill={true} color="purple">
            <ArrowKeyRight/>
        </Button>
    </div>
</Card>