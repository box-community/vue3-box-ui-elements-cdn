<template>
    <div id="box-content-uploader"></div>
</template>

<script setup>
    import { onUnmounted } from "vue";
    import { useHead } from "@vueuse/head";
    const ContentUploaderJs =
        "https://cdn01.boxcdn.net/platform/elements/16.0.0/en-US/uploader.js";
    const ContentUploaderCss =
        "https://cdn01.boxcdn.net/platform/elements/16.0.0/en-US/uploader.css";

    const props = defineProps({
        folderId: String
    })
  
    const BoxCode = useHead({
        script: [
        {
            type: "text/javascript",
            src: ContentUploaderJs,
            onload: () => {
                const accessToken = import.meta.env.VITE_BOX_DEVELOPER_TOKEN;
                const contentUploader = new Box.ContentUploader();
                contentUploader.show(props.folderId, accessToken , {
                container: "#box-content-uploader",
                });
            }
        },
        ],
        link: [
        {
            rel: "stylesheet",
            href: ContentUploaderCss,
        },
        ],
    });

    onUnmounted(() => {
        BoxCode.dispose()
    })
</script>