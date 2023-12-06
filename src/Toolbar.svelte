<script>
  import { Toolbar, setTheme } from "@dhx/trial-suite";
  import { onMount } from "svelte";
  let node, toolbar;
  let contrast = false;
  let theme = "light";
  onMount(() => {
    toolbar = new Toolbar(node, {
      data: [
        {
          id: "topMenuButton",
          type: "button",
          value: "Toolbar button",
          view: "flat",
          icon: "dxi dxi-plus",
          size: "small",
          circle: true,
          color: "secondary",
        },

        {
          id: "theme",
          circle: true,
          icon: "mdi mdi-weather-night",
          checked: false,
        },

        {
          id: "contrast",
          twoState: true,
          active: contrast,
          icon: "mdi mdi-contrast-circle",
        },

        {
          type: "spacer",
        },
        {
          id: "topmenuLinks",
          icon: "mdi mdi-earth",
          tooltip: "Links",
          type: "button",
          view: "link",
          color: "secondary",
          circle: true,
        },
        {
          id: "setting",
          icon: "mdi mdi-cog",
          tooltip: "Setting",
          type: "button",
          view: "link",
          color: "secondary",
          circle: true,
        },
        {
          id: "topmenuInfo",
          icon: "mdi mdi-alert-circle-outline",
          tooltip: "Info",
          type: "button",
          view: "link",
          color: "secondary",
          circle: true,
        },
        {
          id: "avatar",
          type: "imageButton",
          src: "https://snippet.dhtmlx.com/codebase/data/common/img/02/avatar_63.jpg",
          count: 15,
        },
      ],
    });
    toolbar.events.on("click", (id) => {
      switch (id) {
        case "theme": {
          const checked = !toolbar.data.getItem("theme").checked;
          toolbar.data.update("theme", {
            checked,
            icon: `mdi mdi-${
              !checked ? "weather-night" : "white-balance-sunny"
            }`,
          });
          theme = checked ? "dark" : "light";
          break;
        }
        case "contrast": {
          contrast = !contrast;
        }
      }
    });
    return () => toolbar.destructor();
  });

  // @ts-ignore
  $: setTheme(`${contrast ? "contrast-" : ""}${theme}`);
</script>

<div bind:this={node} class="container"></div>

<style>
  .container {
    border-bottom: var(--dhx-border);
  }
</style>
