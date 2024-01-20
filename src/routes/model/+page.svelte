<script>
  import Button from "$lib/components/ui/button/button.svelte";
</script>

<svelte:head>
  <title>Dataset Model & Tech</title>
</svelte:head>

<div class="bg-white px-6 py-20 lg:px-8">
  <div class="mx-auto max-w-3xl">
    <div class="px-4 sm:px-0">
      <h3 class="text-base font-semibold leading-7 text-gray-900">
        Data Model Details (Fruit Detection)
      </h3>
      <p class="mt-1 max-w-2xl text-sm leading-6 text-gray-500">
        Detailed description of the data model and Tech used to Build the
        Application
      </p>
    </div>
    <div class="mt-6 border-t border-gray-100">
      <dl class="divide-y divide-gray-100">
        <div class="px-4 py-6 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-0">
          <dt class="text-sm font-medium leading-6 text-gray-900">
            Images Used
          </dt>
          <dd
            class="mt-1 text-sm leading-6 text-gray-700 sm:col-span-2 sm:mt-0"
          >
            1055 Images of 5 different fruits
          </dd>
        </div>
        <div class="px-4 py-6 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-0">
          <dt class="text-sm font-medium leading-6 text-gray-900">
            Dataset Split
          </dt>
          <dd
            class="mt-1 text-sm leading-6 text-gray-700 sm:col-span-2 sm:mt-0"
          >
            <Button variant="outline" class="border-emerald-500"
              >Train Set <span
                class="font-mono ml-2 font-semibold text-blue-600">93%</span
              ></Button
            >
            <Button variant="outline" class="border-emerald-500"
              >Valid Set <span
                class="font-mono ml-2 font-semibold text-blue-600">3%</span
              ></Button
            >
            <Button variant="outline" class="border-emerald-500"
              >Test Set <span class="font-mono ml-2 font-semibold text-blue-600"
                >4%</span
              ></Button
            >
          </dd>
        </div>
        <div class="px-4 py-6 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-0">
          <dt class="text-sm font-medium leading-6 text-gray-900">
            Roboflow API
          </dt>
          <dd
            class="mt-1 text-sm leading-6 text-gray-700 sm:col-span-2 sm:mt-0"
          >
            <a
              href="https://universe.roboflow.com/fruit-detection-w707e/fruit-detection-deqvb"
              class="underline text-blue-700"
              target="_blank">Link</a
            >
          </dd>
        </div>
        <div class="px-4 py-6 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-0">
          <dt class="text-sm font-medium leading-6 text-gray-900">
            Project Framework
          </dt>
          <dd
            class="mt-1 text-sm leading-6 text-gray-700 sm:col-span-2 sm:mt-0"
          >
            Sveltekit
          </dd>
        </div>
        <div class="px-4 py-6 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-0">
          <dt class="text-sm font-medium leading-6 text-gray-900">About</dt>
          <dd
            class="mt-1 text-sm leading-6 text-gray-700 sm:col-span-2 sm:mt-0"
          >
            <!-- content on  Fruit detection of apple, pineapple, onion, tomato -->

            Fruit detection of apple, pineapple, onion, tomato and watermelon is
            done using Roboflow API. The model is trained on 1055 images of 5
            different fruits. The dataset is split into 93% train, 3% valid and
            4% test set. The model is trained for 100 epochs with a batch size
            of 32. The model is trained on a GPU. The model is deployed using
            Sveltekit.
          </dd>
        </div>
        <div class="px-4 py-6 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-0">
          <dt class="text-sm font-medium leading-6 text-gray-900">
            Object Detection Algorithm
          </dt>
          <dd class="mt-2 text-sm text-gray-900 sm:col-span-2 sm:mt-0">
            <!-- List of Object Detection library in Python -->
            Region-based Convolutional Neural Networks (R-CNN),Faster R-CNN, YOLO,
            RetinaNet
          </dd>
        </div>
        <div class="px-4 py-6 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-0">
          <dt class="text-sm font-medium leading-6 text-gray-900">
            Python Library
          </dt>
          <dd class="mt-2 text-sm text-gray-900 sm:col-span-2 sm:mt-0">
            <!-- List of Object Detection library in Python -->
            Open CV, YOLO, NumPy,Scikit-learn
          </dd>
        </div>
      </dl>
    </div>
  </div>
</div>
<!-- sources : https://neptune.ai/blog/object-detection-algorithms-and-libraries -->
