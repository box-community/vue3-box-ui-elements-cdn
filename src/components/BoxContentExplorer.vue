<template>
    <div id="box-content-explorer"></div>
</template>
  
<script setup>
    import { onUnmounted } from "vue";
    import { useHead } from "@vueuse/head";
    const ContentExplorerJs =
        "https://cdn01.boxcdn.net/platform/elements/16.0.0/en-US/explorer.js";
    const ContentExploredCss =
        "https://cdn01.boxcdn.net/platform/elements/16.0.0/en-US/explorer.css";

    const props = defineProps({
        folderId: String
    })
  
    const BoxCode = useHead({
        script: [
        {
            type: "text/javascript",
            src: ContentExplorerJs,
            onload: () => {
                const accessToken = import.meta.env.VITE_BOX_DEVELOPER_TOKEN;
                const contentExplorer = new Box.ContentExplorer();
                contentExplorer.show(props.folderId, accessToken , {
                container: "#box-content-explorer",
                });
            }
        },
        ],
        link: [
        {
            rel: "stylesheet",
            href: ContentExploredCss,
        },
        ],
    });

    onUnmounted(() => {
        BoxCode.dispose()
    })
</script>