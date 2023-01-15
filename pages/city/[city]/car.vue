<template>
  <div
    class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px16 pb-16 w-3/5"
  >
    <div class="mt-32 flex">
      <!-- Car sideBar -->
      <CarSideBar />
      <!-- Car sideBar -->
      <NuxtPage />
    </div>
  </div>
</template>

<script setup>
const route = useRoute();

function toTitleCase(str) {
  return str.replace(/\w\S*/g, function (txt) {
    return txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase();
  });
}

useHead({
  title: `${
    route.params.make ? toTitleCase(route.params.make) : "Cars"
  } in ${toTitleCase(route.params.city)}`,
});
</script>

<style lang="scss" scoped></style>
