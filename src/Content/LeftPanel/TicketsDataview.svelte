<script>
  import { DataView } from "@dhx/trial-suite";
  import "@dhx/trial-suite/codebase/suite.min.css"
  import { onMount } from "svelte";
  let node, dataview;

  function template({ title, text, type, avatar, name, comments, time }) {
    return `
            <div class="dhx_dataview_template_a">
                <div class="dhx_dataview_template_a__head">
                    <div class="dhx_dataview_template_a__type dhx_dataview_template_a__type--${type}">${type}</div>
                    <div class="dhx_dataview_template_a__content">
                        <div class="dhx_dataview_template_a__title">${title}</div>
                        <div class="dhx_dataview_template_a__comment">${text}</div>
                    </div>
                </div>
                <div class="dhx_dataview_template_a__body">
                    <div class="dhx_dataview_template_a__person">
                        <div class="dhx_dataview_template_a__avatar" style="background-image: url(${avatar})"></div>
                        <div class="dhx_dataview_template_a__info">
                            <div class="dhx_dataview_template_a__time">${time}</div>
                            <div class="dhx_dataview_template_a__name">${name}</div>
                        </div>
                    </div>
                    <div class="dhx_dataview_template_a__comments">${comments}
                    <span class="mdi mdi-comment-outline"></span></div>
                </div>
            </div>
        `;
  }

  onMount(() => {
    dataview = new DataView(node, {
      template,
      data: [
        {
          title: "Ticket for Technical Support #T742",
          text: "Need some support to add a new widget to Dashboard.",
          type: "major",
          avatar:
            "https://snippet.dhtmlx.com/codebase/data/common/img/02/avatar_14.jpg",
          name: "Margaret King",
          comments: "0",
          time: "12:15",
        },
        {
          title: "Ticket for Sales Manager #S210",
          text: "Can you tell me about pricing plans? I didn't understand the difference.",
          type: "minor",
          avatar:
            "https://snippet.dhtmlx.com/codebase/data/common/img/02/avatar_13.jpg",
          name: "Patsy Rhyne",
          comments: "2",
          time: "12:15",
        },
        {
          title: "Ticket for Marketing Manager #M112",
          text: "Want to mention our scheduler case study in your social media. The company has to be mentioned.",
          type: "minor",
          avatar:
            "https://snippet.dhtmlx.com/codebase/data/common/img/02/avatar_06.jpg",
          name: "Ravi Chakrabarti",
          comments: "6",
          time: "12:15",
        },
        {
          title: "Ticket for Account Manager #A984",
          text: "The trial period will end next week. Can you make a discount for us?",
          type: "normal",
          avatar:
            "https://snippet.dhtmlx.com/codebase/data/common/img/02/avatar_04.jpg",
          name: "Lucy Miller",
          comments: "1",
          time: "12:15",
        },
        {
          title: "Ticket for QA #Q394",
          text: "I found a bug. When I change the skin settings some buttons don't change.",
          type: "major",
          avatar:
            "https://snippet.dhtmlx.com/codebase/data/common/img/02/avatar_10.jpg",
          name: "Michael Willis",
          comments: "4",
          time: "12:15",
        },
        {
          title: "Ticket for Technical Support #T741",
          text: "I can't sign in to my account. Maybe I entered wrong password, help me!",
          type: "major",
          avatar:
            "https://snippet.dhtmlx.com/codebase/data/common/img/02/avatar_11.jpg",
          name: "Casey Garcia",
          comments: "0",
          time: "12:15",
        },
      ],
      itemsInRow: 2,
      css: "dhx_dataview_template_a_box",
    });

    return () => dataview.destructor();
  });
</script>

<div bind:this={node} />

<style>
    
</style>
