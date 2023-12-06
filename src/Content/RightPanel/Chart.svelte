<script>
  // @ts-nocheck

  import { Chart } from "@dhx/trial-suite";
  import { onMount } from "svelte";
  let node, chart;

  onMount(() => {
    chart = new Chart(node, {
      type: "pie",
      series: [
        {
          value: "value",
          monochrome: "#0288D1",
          opacity: "opacity",
          text: "month",
          stroke: "#FFFFFF",
          strokeWidth: 0,
        },
      ],
      legend: {
        values: {
          id: "value",
          text: "id",
          color: "color",
        },
        monochrome: "#0288D1",
        align: "right",
        valign: "middle",
        width: 30,
      },
    });

    chart.data.parse([
      { id: "Jan", value: 44.33, month: "Jan", color: "#0288D1", opacity: 1 },
      { id: "Feb", value: 22.12, month: "Feb", color: "#0288D1", opacity: 0.4 },
      { id: "Mar", value: 53.21, month: "Mar", color: "#0288D1", opacity: 0.6 },
      { id: "Apr", value: 34.25, month: "Apr", color: "#0288D1", opacity: 0.2 },
      { id: "May", value: 24.65, month: "May", color: "#0288D1", opacity: 0.1 },
    ]);

    return () => chart.destructor();
  });
</script>

<div bind:this={node} />
