<script>
  let links = [
    {
      url: "#/",
      text: "Home",
    },
    {
      url: "#/about",
      text: "About",
    },
  ];

  // Hanlde the menu icon
  document.addEventListener("DOMContentLoaded", () => {
    // Get all "navbar-burger" elements
    const burger = document.querySelector(".navbar-burger");
    const links = document.querySelector(".navbar-menu");
    const items = document.querySelectorAll(".navbar-item");
    burger.addEventListener("click", () => {
      links.classList.toggle("is-active");
    });
    items.forEach((i) => {
      i.addEventListener("click", () => {
        if (links.classList.contains("is-active")) {
          links.classList.toggle("is-active");
        }
      });
    });
  });
</script>

<nav class="navbar is-fixed-top" aria-label="main navigation">
  <div class="container">
    <div class="navbar-brand">
      <a class="navbar-item is-size-4" href="#/">
        <span class="icon-text">
          <span><strong>Stick With It!</strong></span>
        </span>
      </a>

      <!-- svelte-ignore a11y-missing-attribute -->
      <a
        role="button"
        class="navbar-burger"
        aria-label="menu"
        aria-expanded="false"
        data-target="navbarBasicExample"
      >
        <span aria-hidden="true" />
        <span aria-hidden="true" />
        <span aria-hidden="true" />
      </a>
    </div>

    <div id="navbarBasicExample" class="navbar-menu">
      <div class="navbar-end">
        {#each links as link}
          <a class="navbar-item" href={link.url}>
            {link.text}
          </a>
        {/each}
      </div>
    </div>
  </div>
</nav>
