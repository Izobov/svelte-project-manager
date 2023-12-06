<script>
  import { Chart, Layout } from "@dhx/trial-suite";
  import { onMount } from "svelte";

  let node, accordion, chart;

  onMount(() => {
    accordion = new Layout(node, {
      type: "line",
      rows: [
        {
          header: "HOTELS",
          height: "500px",
          padding: 40,
          id: "chart",
          collapsable: true,
        }
      ],
    });
    chart = new Chart(null, {
      type: "bar",
      scales: {
        bottom: {
          text: "month",
        },
        left: {
          maxTicks: 10,
          max: 100,
          min: 0,
        },
      },
      series: [
        {
          id: "A",
          value: "Won deals",
          color: "none",
          fill: "#0288D1",
          showText: true,
          showTextTemplate: (sum) => `$${sum}`,
        },
        {
          id: "B",
          value: "Lost deals",
          color: "none",
          fill: "rgba(2, 136, 209, 0.6)",
          showText: true,
          showTextTemplate: (sum) => `$${sum}`,
        },
        {
          id: "all",
          value: "All deals",
          color: "none",
          fill: "rgba(94, 131, 186, 0.6)",
          type: "area",
          strokeWidth: 0,
        },
      ],
      legend: {
        series: ["A", "B", "all"],
        halign: "right",
        valign: "top",
        itemPadding: 20,
        margin: 40,
      },
    });
    chart.data.parse([
      { month: "Jan.", "Won deals": 35, "Lost deals": 14, "All deals": 40 },
      { month: "Feb.", "Won deals": 80, "Lost deals": 59, "All deals": 94 },
      { month: "Mar.", "Won deals": 35, "Lost deals": 62, "All deals": 48 },
      { month: "Apr.", "Won deals": 45, "Lost deals": 13, "All deals": 59 },
      { month: "May.", "Won deals": 45, "Lost deals": 22, "All deals": 59 },
      { month: "Jun.", "Won deals": 74, "Lost deals": 52, "All deals": 90 },
      { month: "Jul.", "Won deals": 85, "Lost deals": 78, "All deals": 98 },
    ]);
    accordion.getCell("chart").attach(chart);
    return () => {
        accordion.destructor();
        chart.destructor();
        
    }
  });
</script>

<div bind:this={node}></div>
