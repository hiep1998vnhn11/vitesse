<script lang="ts" setup>
const route = useRoute()
console.log(route.matched.some(record => record.meta.auth))
</script>

<template>
  <div :class="$style.about">
    {{ route }}
    <div :class="$style.about__me">
      123123
    </div>
    <div :id="$style.test">
      Test
    </div>
  </div>
</template>

<style module lang="scss">
.about {
  padding: 20px;
  background: red;
  &__me {
    background: yellow;
  }
}

#test {
  background: blue;
}
</style>
