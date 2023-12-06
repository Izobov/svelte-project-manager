<script>
  import { Toolbar } from "@dhx/trial-suite";
  import { onMount } from "svelte";
  let node, toolbar;

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
  });
</script>

<div bind:this={node}></div>
