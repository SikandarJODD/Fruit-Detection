<script>
  import AppStructImage from "$lib/structure.svg";
  import DataSplit from "$lib/data-split.png";
  import { CodeBlock } from "svhighlight";
  import "highlight.js/styles/base16/dracula.css";
  let focusBlocks = [
    { lines: "", text: "Remove Blur" },
    { lines: "3-13", scrollLine: 1, text: "1: Roboflow API" },
    { lines: "2", scrollLine: 8, text: "2: Function" },
  ];
  let code =
    `<` +
    `script>
    import axios from "axios";
    let getData = async () => {
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
      return res.data;
    };
  <script` +
    `/>`;
</script>

<div class="bg-white px-6 py-32 lg:px-8">
  <div class="mx-auto max-w-3xl text-base leading-7 text-gray-700">
    <p class="text-base font-semibold leading-7 text-indigo-600">Introducing</p>
    <h1
      class="mt-2 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl"
    >
      Fruit Detection with Ripeness Detection
    </h1>
    <p class="mt-6 text-xl leading-8">
      Here we are using a pre-trained model to detect the fruit and then we are
      using a custom model to detect the ripeness of the fruit.
    </p>
    <div class="mt-10 max-w-2xl">
      <p>
        Use of <a
          class="underline"
          target="_blank"
          href="https://universe.roboflow.com">Roboflow API</a
        > to detect the fruits Apple, Watermelon, PineApple, Onions, Tomato
      </p>
      <!-- <ul role="list" class="mt-8 max-w-xl space-y-8 text-gray-600">
        <li class="flex gap-x-3">
          <svg
            class="mt-1 h-5 w-5 flex-none text-indigo-600"
            viewBox="0 0 20 20"
            fill="currentColor"
            aria-hidden="true"
          >
            <path
              fill-rule="evenodd"
              d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z"
              clip-rule="evenodd"
            />
          </svg>
          <span
            ><strong class="font-semibold text-gray-900">Data types.</strong> Lorem
            ipsum, dolor sit amet consectetur adipisicing elit. Maiores impedit perferendis
            suscipit eaque, iste dolor cupiditate blanditiis ratione.</span
          >
        </li>
        <li class="flex gap-x-3">
          <svg
            class="mt-1 h-5 w-5 flex-none text-indigo-600"
            viewBox="0 0 20 20"
            fill="currentColor"
            aria-hidden="true"
          >
            <path
              fill-rule="evenodd"
              d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z"
              clip-rule="evenodd"
            />
          </svg>
          <span
            ><strong class="font-semibold text-gray-900">Loops.</strong> Anim aute
            id magna aliqua ad ad non deserunt sunt. Qui irure qui lorem cupidatat
            commodo.</span
          >
        </li>
        <li class="flex gap-x-3">
          <svg
            class="mt-1 h-5 w-5 flex-none text-indigo-600"
            viewBox="0 0 20 20"
            fill="currentColor"
            aria-hidden="true"
          >
            <path
              fill-rule="evenodd"
              d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z"
              clip-rule="evenodd"
            />
          </svg>
          <span
            ><strong class="font-semibold text-gray-900">Events.</strong> Ac tincidunt
            sapien vehicula erat auctor pellentesque rhoncus. Et magna sit morbi
            lobortis.</span
          >
        </li>
      </ul> -->
      <!-- <p class="mt-8">
        Et vitae blandit facilisi magna lacus commodo. Vitae sapien duis odio id
        et. Id blandit molestie auctor fermentum dignissim. Lacus diam tincidunt
        ac cursus in vel. Mauris varius vulputate et ultrices hac adipiscing
        egestas. Iaculis convallis ac tempor et ut. Ac lorem vel integer orci.
      </p> -->
      <h2 class="mt-8 mb-6 text-2xl font-bold tracking-tight text-gray-900">
        API Code for Fruit Detection by Bytes - Babe :
      </h2>
      <div>
        <CodeBlock
          language="svelte"
          {code}
          {focusBlocks}
          showFocusButtons={true}
        />
      </div>
    </div>
    <h2 class="mt-16 text-2xl font-bold tracking-tight text-gray-900">
      High Level Design of Application
    </h2>
    <figure class="mt-3">
      <img
        class="aspect-video rounded-xl bg-gray-50 object-cover"
        src={AppStructImage}
        alt="hhd-application"
      />
    </figure>
    <h2 class=" z-20 mt-16 text-2xl font-bold tracking-tight text-gray-900">
      Data Split of Model Training
    </h2>
    <img
      class="aspect-video rounded-xl object-contain h-full w-full md:-mt-36 z-10"
      src={DataSplit}
      alt="data-split"
    />
    <!-- <div class="md:-mt-32 max-w-2xl">
      <h2 class="text-2xl font-bold tracking-tight text-gray-900">
        Everything you need to get up and running
      </h2>
      <p class="mt-6">
        Purus morbi dignissim senectus mattis adipiscing. Amet, massa quam
        varius orci dapibus volutpat cras. In amet eu ridiculus leo sodales
        cursus tristique. Tincidunt sed tempus ut viverra ridiculus non
        molestie. Gravida quis fringilla amet eget dui tempor dignissim.
        Facilisis auctor venenatis varius nunc, congue erat ac. Cras fermentum
        convallis quam.
      </p>
      <p class="mt-8">
        Faucibus commodo massa rhoncus, volutpat. Dignissim sed eget risus enim.
        Mattis mauris semper sed amet vitae sed turpis id. Id dolor praesent
        donec est. Odio penatibus risus viverra tellus varius sit neque erat
        velit.
      </p>
    </div> -->
  </div>
</div>
