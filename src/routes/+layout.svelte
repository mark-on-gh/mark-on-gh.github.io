<script>
  import "../tailwind.css";
  import "../app.css";

  let header_links = ["/", "/resume"];

  let acc_links = [
    {
      href: "https://github.com/mark-on-gh/",
      site: "github",
    },
    {
      href: "https://www.linkedin.com/in/mark-joshua-ignacio-14638a24b/",
      site: "linkedin",
    },
    {
      href: "https://mj-on-itch.itch.io/",
      site: "itch",
    },
  ];
</script>

<svelte:head>
  <title>Mark on WWW</title>
</svelte:head>

<nav class="lg:fixed top-5 left-5">
  <ul>
    {#each header_links as href}
      <li class="m-1">
        <a class="text-xl font-mono p-1" {href}>{href}</a>
      </li>
    {/each}
  </ul>
</nav>

<aside class="lg:fixed top-5 right-5">
  <ul class="lg:grid grid-cols-2 max-w-max flex">
    {#each acc_links as link, i}
      <li class="m-1 w-10">
        <a href={link.href}>
          <img src="/{link.site}.svg" alt="{link.site} logo" />
        </a>
      </li>
      {#if i % 2 === 0}
        <li></li>
        <li></li>
      {/if}
    {/each}
  </ul>
</aside>

<main>
  <br />
  <slot />
</main>
