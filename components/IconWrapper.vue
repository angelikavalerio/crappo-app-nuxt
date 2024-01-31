<template>
  <div class="wrapper">
    <slot />
  </div>
</template>

<style lang="scss">
.wrapper {
    position: relative;

    .icon {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
}
</style>
