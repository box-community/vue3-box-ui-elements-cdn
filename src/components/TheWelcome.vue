<script setup>
import WelcomeItem from "./WelcomeItem.vue";
import DocumentationIcon from "./icons/IconDocumentation.vue";
import ToolingIcon from "./icons/IconTooling.vue";
</script>

<template>
  <WelcomeItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>Vue3 & Vite</template>

    Vue’s
    <a href="https://vuejs.org/" target="_blank" rel="noopener"
      >official documentation</a
    >
    provides you with all information you need to get started. This project is served and bundled with
    <a
      href="https://vitejs.dev/guide/features.html"
      target="_blank"
      rel="noopener"
      >Vite</a
    >
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <ToolingIcon />
    </template>
    <template #heading>UI Box Elements</template>

    <a
      href="https://developer.box.com/guides/embed/ui-elements/"
      target="_blank"
      rel="noopener"
      >Box UI Elements
    </a>
    are pre-built UI components that allow developers to add elements of the main Box web application into their own applications. 
  </WelcomeItem>
</template>
