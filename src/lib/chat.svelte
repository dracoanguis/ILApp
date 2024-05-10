<script lang="ts">
    import { ArrowKeyRight, Button, Card, Input } from "flowbite-svelte";

</script>


<Card class="shadow-md m-10 max-w-full">
    <Card>

    </Card>
    <div class="flex flex-row my-2 justify-around">
        <Input placeholder="Your message"/>
        <Button pill={true}>
            <ArrowKeyRight/>
        </Button>
    </div>
</Card>