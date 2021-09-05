<template>
  <h1 class="segment-title"
    v-motion
    :initial="{ x: -200 }"
    :enter="{ x: 0 }">
    <slot></slot>
  </h1>
</template>