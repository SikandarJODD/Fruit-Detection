<!-- Simple Dark -->
<script>
  import { page } from "$app/stores";
  import { Code, Database, GanttChart, Home, X } from "lucide-svelte";
  import { slide } from "svelte/transition";
  let nav = {
    img: "https://cdn-icons-png.flaticon.com/512/5769/5769490.png",
    listnavs: [
      {
        name: "Home",
        link: "/",
        icon: Home,
      },
      {
        name: "Code",
        link: "/code",
        icon: Code,
      },
      {
        name: "Models & Tech",
        link: "/model",
        icon: Database,
      },
      //   {
      //     name: "About",
      //     link: "/about",
      //   },
    ],
  };

  $: isActive = $page.route.id;

  let isMobileMenu = false;
</script>

<nav class="bg-white border-b border-primary">
  <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
    <div class="flex h-14 items-center justify-between">
      <div class="flex items-center w-full">
        <div class="flex-shrink-0 text-primary font-mono text-lg">
          <h1>Bytes-Babe</h1>
        </div>
        <!-- Change Justify-center to end, start -->
        <div class="hidden sm:ml-6 sm:flex w-full justify-center">
          <div class="flex space-x-4">
            {#each nav.listnavs as item}
              <a
                href={item.link}
                class="{isActive === item.link
                  ? ' text-blue-600'
                  : 'text-gray-600  transition-all duration-200 hover:text-primary'}  rounded-md px-3 py-2 text-sm flex items-center gap-1.5 font-medium border border-transparent hover:border-primary"
              >
                <svelte:component
                  this={item.icon}
                  strokeWidth="1.5"
                  size="18"
                />
                {item.name}</a
              >
            {/each}
          </div>
        </div>
      </div>

      <div class="-mr-2 flex sm:hidden">
        <!-- Mobile menu button -->
        <button
          type="button"
          class="relative inline-flex items-center justify-center border-none outline-none p-2"
          aria-controls="mobile-menu"
          aria-expanded="false"
          on:click={() => (isMobileMenu = !isMobileMenu)}
        >
          <span class="absolute -inset-0.5" />
          <span class="sr-only">Open main menu</span>
          <GanttChart
            class="{isMobileMenu
              ? 'hidden'
              : 'block'}  outline-none border-none h-6 w-6"
            strokeWidth="2"
          />
          <X
            class="{isMobileMenu ? 'block' : 'hidden'}  h-6 w-6"
            strokeWidth="1.6"
          />
        </button>
      </div>
    </div>
  </div>

  <!-- Mobile menu, show/hide based on menu state. -->
  {#key isMobileMenu}
    <div
      class="sm:hidden {isMobileMenu ? 'block' : 'hidden'}"
      id="mobile-menu"
      in:slide={{ duration: 300, delay: 50 }}
      out:slide={{ duration: 300 }}
    >
      <div class="space-y-1 px-2 pb-3 pt-2">
        <!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
        {#each nav.listnavs as item}
          <a
            href={item.link}
            class="{isActive === item.link
              ? 'bg-gray-900 text-white'
              : 'text-gray-800 hover:bg-gray-700 hover:text-white'}  flex items-center gap-1.5 rounded-md px-3 py-2 text-base font-medium"
          >
            <svelte:component this={item.icon} strokeWidth="1.5" size="18" />
            {item.name}</a
          >
        {/each}
      </div>
    </div>
  {/key}
</nav>
