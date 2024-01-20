<script>
  // import { onMount } from "svelte";
  // import axios from "axios";
  // let image =
  //   "https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcSTd2wFSt2IoosM0aJyRxAZD1vADVqHzogyQdUhkso3ggbE5Cp3";
  // let quotes;
  // let error = null;
  // onMount(async () => {
  //   try {
  //     let res = await axios({
  //       method: "POST",
  //       url: "https://detect.roboflow.com/fruit-detection-deqvb/1",
  //       params: {
  //         api_key: "kFFRpRYOwJngSCHvwvdf",
  //         confidence: 40,
  //         overlap: 30,
  //         format: "json",
  //         image: image,
  //       },
  //     });
  //     quotes = res.data;
  //   } catch (e) {
  //     error = e;
  //   }
  // });

  import Hero from "$lib/home/Hero.svelte";
</script>

<!-- 
  less than 70 than unripe
  more than 70 than ripes -->

<Hero />
