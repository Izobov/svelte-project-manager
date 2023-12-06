<script>
    import {Sidebar} from "@dhx/trial-suite"
   import { onMount } from 'svelte';

  let sidebar, node;

  const data = [
        {
            id: "toggle",
            css: "toggle-button",
            icon: "mdi mdi-backburger",
        },
        {
            type: "customHTML",
            id: "userInfo",
            css: "user-info_item",
            html:
                "<div class='user-info_container'>" +
                "<img class='user-info_avatar' src='https://snippet.dhtmlx.com/codebase/data/common/img/02/avatar_63.jpg'/>" +
                "<div class='user-info_title'>" +
                "Gloria McKinney" +
                "</div>" +
                "<div class='user-info_contact'>" +
                "@gmckinney" +
                "</div>" +
                "</div>",
        },
        {
            type: "separator",
        },
        {
            id: "today",
            value: "Today",
            icon: "mdi mdi-calendar-star",
        },
        {
            id: "overdue",
            value: "Overdue",
            icon: "mdi mdi-calendar-start",
        },
        {
            id: "unscheduled",
            value: "Unscheduled",
            icon: "mdi mdi-calendar-blank",
        },
        {
            type: "separator",
        },
        {
            id: "projects",
            value: "Projects",
            icon: "mdi mdi-folder-star-outline",
            items: [
                {
                    id: "project1",
                    value: "Project 1",
                    icon: "mdi mdi-plus",
                },
                {
                    id: "project2",
                    value: "Project 2",
                    icon: "mdi mdi-plus",
                },
                {
                    id: "project3",
                    value: "Project 3",
                    icon: "mdi mdi-plus",
                },
            ],
        },
        {
            type: "separator",
        },
        {
            id: "assigned",
            value: "Assigned",
            icon: "mdi mdi-account-search-outline",
            items: [
                {
                    id: "person1",
                    value: "Person 1",
                    icon: "mdi mdi-plus",
                },
                {
                    id: "person2",
                    value: "Person 2",
                    icon: "mdi mdi-plus",
                },
                {
                    id: "Person3",
                    value: "person 3",
                    icon: "mdi mdi-plus",
                },
            ],
        },
        {
            type: "separator",
        },
        {
            type: "spacer",
        },
        {
            type: "separator",
        },
        {
            id: "notification",
            value: "Notification",
            count: 18,
            icon: "mdi mdi-bell-outline",
            countColor: "#D60000",
        },
        {
            id: "configuration",
            value: "Configuration",
            icon: "mdi mdi-tune",
            items: [
                {
                    id: "myAccount",
                    value: "My Account",
                    icon: "mdi mdi-account-settings",
                },
                {
                    id: "general",
                    value: "General Configuration",
                    icon: "mdi mdi-tune",
                },
            ],
        },
    ]

  onMount(() => {
    sidebar = new Sidebar(node, {
        data
    })
    // sidebar = new dhtmlXSideBar({
    //   parent: 'sidebar',
    //   icons_path: 'path/to/icons/',
    //   width: 200,
    //   template: 'icons_text',
    //   items: [
    //     { id: 'dashboard', text: 'Dashboard', icon: 'dashboard.png' },
    //     { id: 'inbox', text: 'Inbox', icon: 'inbox.png' },
    //     { id: 'settings', text: 'Settings', icon: 'settings.png' }
    //   ]
    // });
  });
</script>

<div bind:this={node}></div>

<style>
  div {
    width: fit-content;
    height: 100%;
    border-right: var(--dhx-border);
  }
</style>
