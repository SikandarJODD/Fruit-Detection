<script>
  import Button from "$lib/components/ui/button/button.svelte";
  import { Apple, Citrus, Vegan } from "lucide-svelte";
  import FruitsDec from "./FruitsDec.svelte";
</script>

<div class="flex h-[90vh] w-full flex-col">
  <div class="flex flex-col items-center mt-7">
    <h1 class="text-4xl font-bold text-primary">Fruit Detection</h1>
    <div
      class="my-3 flex items-center justify-center gap-1.5 md:gap-3 md:flex-row flex-wrap"
    >
      <Button variant="outline" class="border-primary">
        <Apple size="20" strokeWidth="1.5" class="mr-1.5" />
        Apple</Button
      >
      <Button variant="outline" class="border-primary">
        <Vegan size="20" strokeWidth="1.5" class="mr-1.5" />
        Pine Apple</Button
      >
      <Button variant="outline" class="border-primary">
        <Citrus size="20" strokeWidth="1.5" class="mr-1.5" />
        WaterMelon</Button
      >
    </div>
  </div>
  <div>
    <FruitsDec />
  </div>
</div>
