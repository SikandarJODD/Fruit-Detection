<script>
  import Button from "$lib/components/ui/button/button.svelte";
  import Input from "$lib/components/ui/input/input.svelte";
  import { Apple, CheckCircle, Citrus, Image, Loader2 } from "lucide-svelte";
  import { scale } from "svelte/transition";
  import axios from "axios";
  let url = "";
  let load = false,
    success = false;
  let fruit_class = "";
  let confidence = 0,
    start = 0;

  let getData = async () => {
    try {
      load = true;
      let res = await await axios({
        method: "POST",
        url: "https://detect.roboflow.com/fruit-detection-deqvb/1",
        params: {
          api_key: "kFFRpRYOwJngSCHvwvdf",
          confidence: 40,
          overlap: 30,
          format: "json",
          image: url,
        },
      });
      let data = res.data;
      confidence = Number(data.predictions[0].confidence * 100);
      confidence = confidence.toFixed(2);
      fruit_class = data.predictions[0].class;
    } catch (e) {
    } finally {
      load = false;
      success = true;
      setTimeout(() => {
        success = false;
      }, 1500);
      let isMatched = setInterval(() => {
        if (start > confidence) {
          clearInterval(isMatched);
        }
        start++;
      }, 50);
    }

    /*
    return : {
        image, time, predictions: [
            {
                class, confidence, height, width, x, y
            }
        ]
    }
    */
  };
</script>

<div class="flex justify-evenly md:mx-64 md:my-10 flex-col md:flex-row">
  <div class=" w-full md:w-1/2 flex item-center justify-evenly">
    <div class="w-full px-5 md:px-2 md:w-9/12 text-center flex flex-col gap-4">
      {#key url}
        {#if url}
          <img
            in:scale
            src={url}
            class=" shadow-md w-full h-56 md:h-72 rounded-xl object-cover object-center overflow-hidden"
            alt="Fruit"
          />
        {:else}
          <div
            class="border w-full h-56 md:h-72 border-primary rounded-xl bg-gray-200"
          ></div>
        {/if}
      {/key}

      <div class="gap-2 flex flex-col">
        <!-- <Button
          ><Image size="20" strokeWidth="1.5" class="mr-1.5" /> Upload Image</Button
        > -->
        <Input
          bind:value={url}
          placeholder="Enter Image URL"
          class="border-primary"
        />
        <Button on:click={getData}>
          {#if load}
            <Loader2 class="mr-1.5 animate-spin" size="20" />
          {/if}
          {#if success}
            <div in:scale>
              <Citrus size="20" strokeWidth="1.5" class="mr-1.5" />
            </div>
          {/if}
          Calculate</Button
        >
      </div>
    </div>
  </div>
  <div
    class="w-full md:w-1/2 justify-center md:justify-start mt-4 md:mt-0 flex"
  >
    <div
      class="flex flex-col gap-2 px-4 justify-center items-center md:justify-start md:items-start"
    >
      <h1 class="text-2xl font-bold text-center">
        Classify the Fruit with Ripness
      </h1>
      <p class="text-xl">
        Confidence : <span class="font-mono text-blue-600">{start}%</span>
      </p>
      <Button class="w-fit">
        {#if fruit_class === "WATERMELON"}
          <!-- content here -->
          <Citrus size="20" strokeWidth="1.5" class="mr-1.5" />
          WaterMelon
        {:else if fruit_class === "APPLE"}
          <Apple size="20" strokeWidth="1.5" class="mr-1.5" />
          Apple
        {:else if fruit_class.length > 0}
          <CheckCircle size="20" strokeWidth="1.5" class="mr-1.5" />
          {fruit_class.toLowerCase()}
        {:else}
          Which Fruit ?
        {/if}
      </Button>
      {#if confidence > 70}
        <p class="capitalize">
          The {fruit_class.toLowerCase()}
          {fruit_class === "ONIONS" ? "are" : "is"} Fresh and you can Consume it.
        </p>
      {:else if confidence < 60 && confidence > 10}
        <p>The {fruit_class.toLowerCase()} is not in Good Condition.</p>
      {:else}
        <p></p>
      {/if}
    </div>
  </div>
</div>
