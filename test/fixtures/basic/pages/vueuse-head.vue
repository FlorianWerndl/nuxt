<script lang="ts" setup>
function useLegacyUseHead () {
  useHead({
    titleTemplate: '%s - VueUse head polyfill test',
  })
}
function useLegacyVueUseHead () {
  // get vm
  const vm = getCurrentInstance()
  const head = vm?.appContext.provides.usehead
  head.addHeadObjs({
    title: 'using provides usehead and updateDOM',
  })
  head.updateDOM()
}

useLegacyUseHead()
useLegacyVueUseHead()
</script>

<template>
  <div>
    <h1>VueUse head polyfill test</h1>
    <!-- This component is only here to make it a shared chunk for test in `styles.vue` -->
    <SharedComponent />
  </div>
</template>
