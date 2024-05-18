<script lang="ts">
    import { ArrowKeyRight, Button, Card, Input } from "flowbite-svelte";

</script>


<Card class="shadow-md m-10 max-w-full">
    <Card >
        Hello, I’m IvaBot! 👋 I’m your personal shopping assistant. How can I help you?
    </Card>
    <Card class="my-5 mx-20" color="purple">
        Find me a colorful dress
    </Card>
    <Card>
        Here are some colorful dresses available on our platform
    </Card>
    <div class="flex flex-row my-2 justify-around">
        <Input placeholder="Your message"/>
        <Button pill={true}>
            <ArrowKeyRight/>
        </Button>
    </div>
</Card>